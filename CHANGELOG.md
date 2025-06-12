# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!-- 
AI Context: This changelog helps AI assistants understand the project's evolution.
Each entry includes not just what changed, but WHY it changed and what patterns emerged.
Key architectural decisions are linked to their ADRs.
-->

## [0.3.0](https://github.com/danielscholl-osdu/mvn-mcp-server/compare/v0.2.0...v0.3.0) (2025-06-12)


### Features

* **ci:** enhance workflow with timeout protection and artifact collection ([ff80b29](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/ff80b291b82e5394b03e118dea2612dd47874703))
* **tests:** add comprehensive MCP server integration tests ([8a5b914](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/8a5b914bb8dd925a1663d762230c5fa0f71f6c37))


### Bug Fixes

* **deps:** upgrade FastMCP from &gt;=2.0.0 to &gt;=2.8.0 ([4d11519](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/4d115195efedad2dd569885743a35bd2a7a0d974))
* **server:** update FastMCP constructor to use instructions parameter ([46fad3f](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/46fad3f7435b278706f03c2cb0ebf4bdcc74ef53))
* **tests:** improve FastMCP 2.8.0 API compatibility for integration tests ([87d94a5](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/87d94a5578c80d03dbb465a170594116e77c770b))

## [0.2.0](https://github.com/danielscholl-osdu/mvn-mcp-server/compare/v0.1.3...v0.2.0) (2025-06-06)


### Features

* **prompts:** add MCP Prompts specification for dependency workflows ([a1e8992](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/a1e899278d8733ca60451cae9c30aa7afaa43171))
* **prompts:** add MCP Prompts specification for dependency workflows ([2de3ffa](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/2de3ffa7662c6befd5469aa78c2a80c2e9390d57))
* **prompts:** implement MCP Prompts and Resources for enterprise workflows ([6c97056](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/6c970562e769af539a7d4049845b516fff9c7426))
* **prompts:** implement MCP Prompts and Resources for enterprise workflows ([c86422a](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/c86422a021f3b95225de9cba21c0d30e776a4a45))


### Bug Fixes

* **copilot:** move setup file to workflows directory and update format ([e31ff8e](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/e31ff8e5e8700e6430362c5ab22eca7b677124c0))
* **copilot:** move setup file to workflows directory and update format ([ea8da65](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/ea8da6515a27ef24970b7e24c8ee63564d1d9a58))
* **tests:** add pytest-asyncio dependency and configuration for CI ([00cb48a](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/00cb48a7e33a59b6881d6db2fcf79fb6740fa82f))

## [0.1.3](https://github.com/danielscholl-osdu/mvn-mcp-server/compare/v0.1.2...v0.1.3) (2025-05-24)


### Bug Fixes

* **ci:** resolve black and flake8 E203 conflict ([36ed1a1](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/36ed1a156f2a02701b81d3871cc3e94e85544040))
* **ci:** resolve black and flake8 E203 conflict ([35b3260](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/35b3260eea23cd7eef6221f1322cf4d20e53b089))

## [0.1.2](https://github.com/danielscholl-osdu/mvn-mcp-server/compare/v0.1.1...v0.1.2) (2025-05-24)


### Bug Fixes

* **ci:** correct black path and flake8 whitespace error ([985b95e](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/985b95e64017e61e3b9c66d471be356de09c8952))

## [0.1.1](https://github.com/danielscholl-osdu/mvn-mcp-server/compare/v0.1.0...v0.1.1) (2025-05-24)


### Bug Fixes

* **deps:** update to fastmcp&gt;=2.0.0 and add httpx dependency ([1af07cf](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/1af07cf0576def77429ebee91612d5b8e05e150a))
* **imports:** update all imports from mcp.server.fastmcp to fastmcp ([bbc11a8](https://github.com/danielscholl-osdu/mvn-mcp-server/commit/bbc11a83396c5f6503341747f7872a9d6179124e))

## [0.1.0] - TBD

_This section will be auto-populated by Release Please when the first release is created._

---

<!-- 
AI Learning Notes:
- The project started with a focus on read operations and gradually added write capabilities
- Security and compliance features were added based on OSDU platform requirements
- The dual permission model emerged from the need to separate data modification from deletion
- Each service client follows the same pattern but has service-specific quirks (e.g., Legal API uses v1)
-->
