# Changelog
All notable changes to this project will be documented in this file. See [conventional commits](https://www.conventionalcommits.org/) for commit guidelines.

- - -
## [v1.2.0](https://github.com/tao3k/omni-devenv-fusion/compare/f869d85de10377cea9de095d67420719a4702704..v1.2.0) - 2026-01-01
#### Features
- (**docs**) add modular stress test framework specification - ([1ce76c5](https://github.com/tao3k/omni-devenv-fusion/commit/1ce76c5ab17372d4f1737b3fac1bf60f33400dc5)) - guangtao
- (**docs**) add advanced search tool spec and update claude documentation - ([34ec8b7](https://github.com/tao3k/omni-devenv-fusion/commit/34ec8b77a0691e5aecc6ffb2dda6c077cd39b260)) - guangtao
- (**mcp**) add ast-grep code intelligence tools for structural search and refactoring - ([749147b](https://github.com/tao3k/omni-devenv-fusion/commit/749147b8fc0373129c3ffa765f988da875058a7a)) - guangtao
- (**mcp**) add instructions loader, lazy cache, and project context framework - ([35eec44](https://github.com/tao3k/omni-devenv-fusion/commit/35eec4403bfe7041507c50a54ae6a53d3e3321da)) - guangtao
- (**mcp**) add Agentic OS with five pillars: Spec Kit, Memory, Flight Recorder, OODA Loop, Smart Publisher - ([e817967](https://github.com/tao3k/omni-devenv-fusion/commit/e817967a8f0f93c21062c010636641caeb641f79)) - guangtao
- (**mcp**) add load_git_workflow_memory tool for gh persistent memory - ([46f241d](https://github.com/tao3k/omni-devenv-fusion/commit/46f241d68010e494a26cc0738bf8585d6ef83026)) - guangtao
- (**mcp**) implement Language Expert System for Router-Augmented Coding - ([54ad72a](https://github.com/tao3k/omni-devenv-fusion/commit/54ad72a1bb64c832c51c4488a628bdf857b1b6ff)) - guangtao
- (**mcp**) implement Docs as Code system with MCP enforcement tools - ([99ab307](https://github.com/tao3k/omni-devenv-fusion/commit/99ab307f9561cf5ee27e9e2a0d0cbc881cd0ad35)) - guangtao
- (**mcp**) complete dual-server architecture with Phase 3 features - ([8f64a16](https://github.com/tao3k/omni-devenv-fusion/commit/8f64a1690ed4ef812920093fe148b92c42eef0ed)) - guangtao
- (**mcp**) add delegate_to_coder bridge tool (Phase 2) - ([75f5c8f](https://github.com/tao3k/omni-devenv-fusion/commit/75f5c8fc9fc7709d97fc6148d5d8152b6ee7c1ac)) - guangtao
- (**mcp**) add micro-level tools and safety enhancements - ([207a104](https://github.com/tao3k/omni-devenv-fusion/commit/207a104b922fb8b7228134b56e315629bf69c76b)) - guangtao
- (**mcp**) add save_file tool for write capabilities (Phase 3) - ([c99444f](https://github.com/tao3k/omni-devenv-fusion/commit/c99444f544280363053d25e8f5421b0cbdfee308)) - guangtao
- (**mcp**) add list_directory_structure tool for token optimization - ([d6aff17](https://github.com/tao3k/omni-devenv-fusion/commit/d6aff17e8198be3dfdd214aca1f11feb19994af9)) - guangtao
- (**mcp-core**) add thread-safe instructions loader with knowledge base - ([51eaa58](https://github.com/tao3k/omni-devenv-fusion/commit/51eaa580a5a2125210e7256ca9d97b00e7162ec1)) - guangtao
- automate claude module management based on secrets status - ([7dce1f3](https://github.com/tao3k/omni-devenv-fusion/commit/7dce1f35f3c2a058d3aca999c6a08e4ff992103a)) - guangtao
- allow orchestrator env from json file - ([a33406e](https://github.com/tao3k/omni-devenv-fusion/commit/a33406e3793ee1e844bfd7097b518c1e9f20f11e)) - GuangTao Zhang
#### Bug Fixes
- (**mcp-core**) resolve threading.Lock deadlock with pure lazy loading - ([f0a919e](https://github.com/tao3k/omni-devenv-fusion/commit/f0a919ecda46686431534bb574cf8b054f43dfd4)) - guangtao
- correct dmerge import and lefthook commands path in lefthook.nix - ([fb9c84e](https://github.com/tao3k/omni-devenv-fusion/commit/fb9c84e4f5eaba7cbbdd5ef939b68b0b1007b1f1)) - guangtao
#### Documentation
- (**cli**) add local developer memory section to project instructions - ([cbe10f2](https://github.com/tao3k/omni-devenv-fusion/commit/cbe10f20c8d3f805362738047a05ad503ed23402)) - guangtao
- (**docs**) update CLAUDE.md to reference docs/how-to/git-workflow.md - ([d7b3ce5](https://github.com/tao3k/omni-devenv-fusion/commit/d7b3ce5a8a098ca24da153256bd7d9a97ecf2ed8)) - guangtao
- (**git-workflow**) update authorization rules for agent commits - ([ed4bc64](https://github.com/tao3k/omni-devenv-fusion/commit/ed4bc64b0a157569bd34519b9749917745908821)) - guangtao
- (**mcp**) add guidelines.md for persistent memory strategy - ([e14f353](https://github.com/tao3k/omni-devenv-fusion/commit/e14f3539eac67d4276098eb877c6318153506fe8)) - guangtao
- reorganize design documents to correct locations - ([6277613](https://github.com/tao3k/omni-devenv-fusion/commit/6277613e670f3bc46f3f8b840d6dcb0ab202798b)) - guangtao
- create agent/knowledge/ for problem-solution knowledge base - ([7c78784](https://github.com/tao3k/omni-devenv-fusion/commit/7c78784fadac90d38bb908c2c9f79bc58d67be0f)) - guangtao
- update git-workflow.md with Agent/LLM commit protocol - ([f8adcac](https://github.com/tao3k/omni-devenv-fusion/commit/f8adcac96d0d4cd289d0f2b74eed8afd58c22ac8)) - guangtao
- simplify CLAUDE.md and add lang_expert documentation - ([ccc6675](https://github.com/tao3k/omni-devenv-fusion/commit/ccc6675d7bfe84d90f7006df7c962a822a80ee83)) - guangtao
- add default rules for config changes and agent-commit protocol - ([59f4b93](https://github.com/tao3k/omni-devenv-fusion/commit/59f4b93937bf0439995b37c837c9c304693b0da8)) - guangtao
- clarify cog and conform roles in git workflow - ([df78076](https://github.com/tao3k/omni-devenv-fusion/commit/df7807622b48ddfad80a0f019a3d5ac452e388e0)) - guangtao
- add commit message standard with project scopes - ([0d411f5](https://github.com/tao3k/omni-devenv-fusion/commit/0d411f564e24df4ddbfcd34eea2a729700bfd450)) - guangtao
- add Agent-Commit Protocol for safe AI git interactions - ([fbd3797](https://github.com/tao3k/omni-devenv-fusion/commit/fbd3797c77ae4677c17ed82dfc15652c29210638)) - guangtao
- enhance Explanation Trilogy with safety and self-healing - ([8f206dc](https://github.com/tao3k/omni-devenv-fusion/commit/8f206dc2464ff41953b3ce27bc5132f3fc5bbc5b)) - guangtao
- add Deep Explanation Trilogy and Diátaxis structure - ([d30092a](https://github.com/tao3k/omni-devenv-fusion/commit/d30092a702dccca7ba27d746cd0da8ac914294d3)) - guangtao
- rewrite Getting Started with writing standards - ([86cf8b7](https://github.com/tao3k/omni-devenv-fusion/commit/86cf8b7ba277d4b7974e4f288f481b582441030a)) - guangtao
- modularize writing standards into library - ([6ffd0c6](https://github.com/tao3k/omni-devenv-fusion/commit/6ffd0c6a1f384bd8ae8869199d19173fddfdc00e)) - guangtao
- rewrite Getting Started as Why document - ([53393f6](https://github.com/tao3k/omni-devenv-fusion/commit/53393f67a5fad70e44e0856b81fda69ce5aa4118)) - guangtao
- rewrite Getting Started as What & Why document - ([e7dc5a4](https://github.com/tao3k/omni-devenv-fusion/commit/e7dc5a4c6241d813204cbdfc9d91f160448a42ed)) - guangtao
- update README and add Getting Started guide - ([ff8494a](https://github.com/tao3k/omni-devenv-fusion/commit/ff8494a0c7c47e3b8f8e0c49fbeaac1f03747c66)) - guangtao
- update CLAUDE.md with new tools and fix passive voice - ([57db90e](https://github.com/tao3k/omni-devenv-fusion/commit/57db90e7ab33ab8e8faaf19204984282082b05dd)) - guangtao
- update CLAUDE.md with new tools and fix passive voice - ([2a7d657](https://github.com/tao3k/omni-devenv-fusion/commit/2a7d6573454361898df42f50c17dd29c834c9ee5)) - guangtao
- add writing standards system with internalization - ([ba7e69c](https://github.com/tao3k/omni-devenv-fusion/commit/ba7e69c103433033b899529a5b5014ccf9031ee7)) - guangtao
#### Tests
- (**mcp**) add comprehensive test suite for all MCP tools - ([83b5d3f](https://github.com/tao3k/omni-devenv-fusion/commit/83b5d3fce1d70e165fcb1de6bd969d603db283a3)) - guangtao
#### Refactoring
- (**inference**) load API key from .mcp.json config file - ([14a15fa](https://github.com/tao3k/omni-devenv-fusion/commit/14a15faf82897cad1a937e90eefa02f8c4846e16)) - guangtao
- (**mcp**) extract shared library mcp_core for dual-server architecture - ([5e69232](https://github.com/tao3k/omni-devenv-fusion/commit/5e692325ee1a69782b5d8f937e97455e04353b83)) - guangtao
- (**mcp**) split into dual-server architecture (Phase 1) - ([7102bc1](https://github.com/tao3k/omni-devenv-fusion/commit/7102bc1cef3c5ed6cf1841959bdeb121bebbb240)) - guangtao
#### Miscellaneous Chores
- (**cli**) add missing scopes for version bump - ([1604212](https://github.com/tao3k/omni-devenv-fusion/commit/1604212992c08dcaef92c3b0d1dacb8d34551ddf)) - guangtao
- (**cli**) fix scopes - ([4e9de75](https://github.com/tao3k/omni-devenv-fusion/commit/4e9de75534d2159d58616bde09c84ab61abb74fe)) - guangtao
- (**docs**) update documentation for Spec-Driven Development and pytest testing - ([90925a0](https://github.com/tao3k/omni-devenv-fusion/commit/90925a084e8899572fa9791a99a9b579fe36b438)) - guangtao
- (**mcp**) add Coder server tests and fix ast-grep commands - ([651e087](https://github.com/tao3k/omni-devenv-fusion/commit/651e087978eda5fcbcd69b624f8c20f4943772c7)) - guangtao
- (**mcp**) remove orphaned personas.py (moved to mcp_core/inference.py) - ([7ce721b](https://github.com/tao3k/omni-devenv-fusion/commit/7ce721b7373c908a0f74cd59c1669e53a2325722)) - guangtao
- (**version**) ready to bump to v1.3.0 - ([65d7cd0](https://github.com/tao3k/omni-devenv-fusion/commit/65d7cd07e6365061bc79472539ce3161ab044c3e)) - guangtao
- remove CHANGELOG for fresh release - ([1de93b8](https://github.com/tao3k/omni-devenv-fusion/commit/1de93b8f5506a08e3cf3ee99a25bf9a92eaf19ca)) - guangtao
- switch secrets provider from 1Password to dotenv - ([1e9c9d6](https://github.com/tao3k/omni-devenv-fusion/commit/1e9c9d68e0a1c18df532a5dac2bb121f9b24dd80)) - guangtao
- remove hunspell and typos from lefthook pre-commit - ([e2c62fc](https://github.com/tao3k/omni-devenv-fusion/commit/e2c62fc894437ad1eb40d02eb75266c0e46f25fd)) - guangtao
- follow numtide/prj-spec for project directories - ([476ff03](https://github.com/tao3k/omni-devenv-fusion/commit/476ff0397ce91aac67167183cc91bf7fd8486f49)) - guangtao
- add mcp test commands and infrastructure - ([e524acf](https://github.com/tao3k/omni-devenv-fusion/commit/e524acfbd013dd4eda643832596d42d0593b6a6e)) - guangtao
- add omnibus devenv inputs filtering example to tool-router - ([4ad856c](https://github.com/tao3k/omni-devenv-fusion/commit/4ad856cd2bdaf8cbeb23c2b360c2b4d56564b9aa)) - guangtao
- add tool-router example protocol to CLAUDE.md - ([5fb4a41](https://github.com/tao3k/omni-devenv-fusion/commit/5fb4a410121155d005ec4d50431186c2a04b4e22)) - guangtao
- add tool-router with nix edit protocol examples - ([7baed74](https://github.com/tao3k/omni-devenv-fusion/commit/7baed74dc682ac920f4dee307f80b0b8db5af5bc)) - guangtao
- add mcp debug commands to justfile - ([9ea9030](https://github.com/tao3k/omni-devenv-fusion/commit/9ea9030d6cc0404251be14d0af17d0307296c287)) - guangtao
- sync with release - ([f869d85](https://github.com/tao3k/omni-devenv-fusion/commit/f869d85de10377cea9de095d67420719a4702704)) - guangtao

- - -

Changelog generated by [cocogitto](https://github.com/cocogitto/cocogitto).