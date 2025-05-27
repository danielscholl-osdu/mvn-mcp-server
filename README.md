# Maven MCP Server

A Model Context Protocol (MCP) server that provides tools for working with Maven dependencies, specifically for checking if specific versions of dependencies exist in the Maven Central repository, retrieving the latest versions, and finding the latest version based on semantic versioning components.

## Setup

### Installation

```bash
# Clone the repository
git clone https://github.com/danielscholl/mvn-mcp-server.git
cd mvn-mcp-server

# Install dependencies
uv sync

# Install the package in development mode
uv pip install -e '.[dev]'

# Run tests to verify installation
uv run pytest
```

### MCP Configuration

To utilize this MCP server directly in other projects either use the buttons to install in VSCode, edit the `.mcp.json` file directory.

> Clients tend to have slighty different configurations

[![Install with UV in VS Code](https://img.shields.io/badge/VS_Code-UV-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect?url=vscode:mcp/install?%7B%22name%22%3A%22mvn-mcp-server%22%2C%22command%22%3A%22uvx%22%2C%22args%22%3A%5B%22run%22%2C%22mvn-mcp-server%22%5D%2C%22env%22%3A%7B%7D%7D)   [![Install with Docker in VS Code](https://img.shields.io/badge/VS_Code-Docker-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect?url=vscode:mcp/install?%7B%22name%22%3A%22mvn-mcp-server%22%2C%22command%22%3A%22docker%22%2C%22args%22%3A%5B%22run%22%2C%22-i%22%2C%22--rm%22%2C%22--mount%22%2C%22type%3Dbind%2Csource%3D%3CYOUR_WORKSPACE_PATH%3E%2Ctarget%3D%2Fworkspace%22%2C%22danielscholl%2Fmvn-mcp-server%22%5D%2C%22env%22%3A%7B%7D%7D)

To use this MCP server in your projects, add the following to your `.mcp.json` file:

```json
{
  "mcpServers": {
    "mvn-mcp-server": {
      "type": "stdio",
      "command": "uv",
      "args": [
        "run",
        "mvn-mcp-server"
      ],
      "env": {}
    }
  }
}
```

## Usage

The MCP server provides several tools for working with Maven dependencies and Java projects. Below are examples of how to use each tool:

### Check Single Version

```
mvn:check_version_tool
Parameters:
- dependency: "group:artifact" (e.g., "org.apache.logging.log4j:log4j-core")
- version: "2.17.1"
- packaging: "jar" (optional, defaults to "jar")
- classifier: null (optional)
```

Checks if a specific version exists and provides update information.

### Batch Version Check

```
mvn:check_version_batch_tool
Parameters:
- dependencies: [
    {"dependency": "org.springframework:spring-core", "version": "5.3.0"},
    {"dependency": "com.fasterxml.jackson.core:jackson-databind", "version": "2.13.0"}
  ]
```

Process multiple dependency checks in a single request.

### List Available Versions

```
mvn:list_available_versions_tool
Parameters:
- dependency: "org.apache.commons:commons-lang3"
- version: "3.12.0" (current version for context)
- include_all_versions: false (optional)
```

Lists all available versions grouped by minor version tracks.

### Scan Java Project

```
mvn:scan_java_project_tool
Parameters:
- workspace: "/path/to/java/project"
- pom_file: "pom.xml" (optional, relative to workspace)
- scan_mode: "workspace" (optional)
- severity_filter: ["CRITICAL", "HIGH"] (optional)
```

Scans Maven projects for security vulnerabilities using Trivy.

### Analyze POM File

```
mvn:analyze_pom_file_tool
Parameters:
- pom_file_path: "/path/to/pom.xml"
- include_vulnerability_check: true (optional)
```

Analyzes a single POM file for dependencies and vulnerabilities.

## Available Tools

### Version Management
- **check_version_tool**: Check a Maven version and get all version update information
- **check_version_batch_tool**: Process multiple Maven dependency version checks in a single batch
- **list_available_versions_tool**: List all available versions grouped by minor version tracks

### Security Scanning  
- **scan_java_project_tool**: Scan Java Maven projects for vulnerabilities using Trivy
- **analyze_pom_file_tool**: Analyze a single Maven POM file for dependencies and vulnerabilities

## Error Handling

All tools return standardized error responses when issues occur:

```json
{
  "tool_name": "[tool_name]",
  "status": "error",
  "error": {
    "code": "[ERROR_CODE]",
    "message": "[Error description]"
  }
}
```

Common error codes include:
- `INVALID_INPUT_FORMAT`: Input parameters are malformed
- `DEPENDENCY_NOT_FOUND`: The requested Maven dependency does not exist
- `VERSION_NOT_FOUND`: The specific version does not exist
- `MAVEN_API_ERROR`: Error connecting to Maven Central
- `INTERNAL_SERVER_ERROR`: Unexpected server error

## Development

### Testing

```bash
# Run all tests
uv run pytest

# Run specific tests
uv run pytest src/mvn_mcp_server/tests/tools/test_check_version.py
```

### Architecture

The server implements a layered architecture:
- **Service Layer**: Core functionality for Maven API interactions, caching, and version handling
- **Tool Layer**: MCP tool implementations that use the service layer
- **Shared Utilities**: Common utilities for validation and error handling

## License

[MIT License](LICENSE)