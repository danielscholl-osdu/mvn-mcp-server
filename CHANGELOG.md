# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!-- 
AI Context: This changelog helps AI assistants understand the project's evolution.
Each entry includes not just what changed, but WHY it changed and what patterns emerged.
Key architectural decisions are linked to their ADRs.
-->

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
