# Release Process Guide

> **Status**: Active
> **Version**: 1.0.0

## 1. Core Problem Analysis

### 1.1 Why Did v1.5.0 Bump Fail Initially?

| Root Cause                                   | Symptom                                                   | Impact                   |
| -------------------------------------------- | --------------------------------------------------------- | ------------------------ |
| Tag not synced with VERSION                  | Cog saw v1.2.0 tag, tried bump to v1.2.x                  | Wrong target version     |
| Stale release/1.2 branch with merge conflict | "Merging is not possible because you have unmerged files" | Bump process stuck       |
| Manual VERSION bump without tag update       | "tag already exists" error                                | Release process confused |

### 1.2 Cog Workflow Gap

```
Current pre_bump_hooks:
  1. echo {{version}} > ./VERSION     ← Sets version FIRST
  2. Create/switch release branch     ← May fail if branch has conflicts
```

**Problem**: If step 2 fails, VERSION is already modified but release branch is broken.

## 2. Version Management Rules

### 2.1 Version States

| State       | VERSION Format | Tag      | Purpose             |
| ----------- | -------------- | -------- | ------------------- |
| Development | `X.Y.0-dev`    | None     | Active development  |
| Release     | `X.Y.0`        | `vX.Y.0` | Published release   |
| Hotfix      | `X.Y.Z`        | `vX.Y.Z` | Patch after release |

### 2.2 Version Numbering

```
MAJOR.MINOR.PATCH
├── MAJOR: Breaking changes, architectural refactoring
├── MINOR: New features, backward-compatible
└── PATCH: Bug fixes, patches
```

### 2.3 State Transition

```
Dev (1.5.0-dev) → Release (1.5.0) → Dev (1.6.0-dev)
        │              │               │
        └─ just bump-minor ─→        └─ just bump-minor
```

## 3. Pre-Release Checklist

### 3.1 Before Running `just bump-minor`

```bash
# 1. Check current state
git status
cat VERSION
git tag | tail -3

# 2. Verify VERSION matches expected version
#    - Dev: X.Y.0-dev
#    - Release: X.Y.0

# 3. Check for stale branches
git branch -a | grep release
git worktree list

# 4. Clean up any old release branches
git branch -D release/X.Y  # If exists and not needed
```

### 3.2 Mandatory Checks

- [ ] All tests pass: `just test`
- [ ] No uncommitted changes (except intentional ones)
- [ ] VERSION is in dev state (X.Y.0-dev)
- [ ] Latest tag reflects current VERSION

### 3.3 Tag Sync Rule

**CRITICAL**: Before any release, ensure tag matches VERSION:

```bash
# If VERSION is 1.4.0 but latest tag is v1.2.0:
git tag -d v1.2.0          # Delete old tag
git tag v1.4.0             # Create correct tag

# Then verify
git tag | tail -3
cat VERSION
```

## 4. Release Process

### 4.1 Standard Minor Release (`just bump-minor`)

```bash
# Pre-conditions:
# - VERSION = X.Y.0-dev
# - Latest tag = v(X-1).Y.0 or lower

just bump-minor
```

**What happens**:

1. Cog bumps VERSION to X.Y.0
2. Creates release/X.Y branch
3. Pushes branch and tag vX.Y.0
4. Merges back to main
5. Sets VERSION to (X+1).Y.0-dev
6. Pushes main

### 4.2 Post-Release Verification

```bash
git status
cat VERSION              # Should be (X+1).Y.0-dev
git tag | tail -3        # Should show vX.Y.0
git log --oneline -3     # Should show sync commit
```

### 4.3 Emergency Hotfix Patch

```bash
# On release/X.Y branch
git checkout release/1.5

# Make fix commits
git add . && git commit -m "fix(scope): description"

# Bump patch version
cog bump --patch

# Or manually:
echo "1.5.1" > VERSION
git add VERSION
git commit -m "chore(version): v1.5.1"
git tag v1.5.1
git switch main
git merge release/1.5 --no-ff -m "chore: merge v1.5.1 hotfix"
echo "1.6.0-dev" > VERSION
git add VERSION
git commit -m "chore(version): start v1.6.0 development"
```

## 5. Recovery Procedures

### 5.1 Stale Release Branch with Merge Conflict

```bash
# Don't try to fix the merge!
git switch main
git branch -D release/X.Y          # Delete stale branch
cog bump --minor                    # Cog will create fresh branch
```

### 5.2 Wrong Tag Created

```bash
# If you created v1.2.0 but needed v1.4.0:
git tag -d v1.2.0                   # Delete wrong tag
git tag v1.4.0                      # Create correct tag
git push origin :refs/tags/v1.2.0   # Push deletion to remote
git push origin v1.4.0              # Push correct tag
```

### 5.3 VERSION Corrupted During Failed Bump

```bash
# Check current VERSION
cat VERSION

# If wrong, restore from last commit
git checkout HEAD -- VERSION

# Or set manually
echo "X.Y.0-dev" > VERSION
```

## 6. Configuration Source of Truth

| File       | Purpose           | Update Via                            |
| ---------- | ----------------- | ------------------------------------- |
| `cog.toml` | Cog configuration | `units/modules/lefthook.nix` (nixago) |
| `VERSION`  | Current version   | Manual or `cog bump`                  |
| Tags       | Release markers   | Manual or `cog bump`                  |

**Key Point**: Never edit `cog.toml` directly. Modify `units/modules/lefthook.nix` and run `direnv reload`.

## 7. Workflow Summary

```
Daily Development:
  1. Work on feature branches
  2. Merge to main
  3. VERSION stays at X.Y.0-dev

Ready to Release:
  1. Verify pre-release checklist (Section 3)
  2. Run: just bump-minor
  3. Verify post-release (Section 4.2)

After Release:
  1. Continue development on X.(Y+1).0-dev
  2. Repeat cycle
```

## 8. Anti-Patterns to Avoid

| Anti-Pattern                                     | Why It's Bad                      | Correct Approach           |
| ------------------------------------------------ | --------------------------------- | -------------------------- |
| Manually editing VERSION without tag update      | Cog confused about target version | Sync tag with VERSION      |
| Force pushing to release branches                | Breaks other collaborators        | Create new branch or PR    |
| Deleting repo/worktree                           | Data loss, context reset          | Use `git reset --soft`     |
| Merging release branch with unresolved conflicts | Broken state                      | Delete and recreate branch |
| Editing cog.toml directly                        | Changes will be overwritten       | Edit lefthook.nix instead  |

## 9. Related Documentation

- [Git Workflow](git-workflow.md) - Commit message standards
- [Feature Lifecycle](../standards/feature-lifecycle.md) - Feature development process
- [CLAUDE.md](../../CLAUDE.md) - Agent instructions

## 10. Quick Reference

```bash
# Check before release
alias pre-release-check='echo "VERSION: $(cat VERSION)" && echo "Tags: $(git tag | tail -3)" && echo "Status: $(git status --short)"'

# Sync tag to VERSION
sync-tag() {
    local version=$(cat VERSION)
    local major_minor=$(echo $version | cut -d. -f1,2)
    git tag -d v$major_minor 2>/dev/null || true
    git tag v$major_minor
    echo "Synced tag to v$major_minor"
}

# Quick release
release() {
    pre-release-check
    sync-tag
    just bump-minor
}
```

---

_Last updated: 2026-01-01_
