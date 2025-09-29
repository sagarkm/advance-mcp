# Advanced MCP Server

A Model Context Protocol (MCP) server built with FastMCP that provides tools and utilities for AI applications.

## Overview

This project implements an MCP server using FastMCP, offering a simple and efficient way to expose tools to MCP-compatible clients like VS Code with GitHub Copilot.

## Features

- **Welcome Tool**: A simple greeting tool that demonstrates basic MCP functionality
- **HTTP Transport**: Uses streamable HTTP for communication
- **FastMCP Framework**: Built on the FastMCP library for easy development and deployment

## Requirements

- Python 3.8+
- uv (Python package manager)

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/sagarkm/advance-mcp.git
   cd advance-mcp
   ```

2. Install dependencies using uv:

   ```bash
   uv sync
   ```

## Usage

### Running the Server

Start the MCP server:

```bash
uv run python main.py
```

The server will start on `http://localhost:3000` by default.

### Connecting to VS Code

1. Open VS Code settings
2. Navigate to your MCP configuration file (usually `mcp.json`)
3. Add the following server configuration:

```json
{
  "servers": {
    "my-alpic-mcp": {
      "type": "http",
      "url": "http://localhost:3000"
    }
  }
}
```

**Important**: Make sure to use `http://` (not `https://`) as the server runs without SSL.

## Available Tools

### Welcome Tool

- **Name**: `welcome`
- **Description**: Returns a friendly welcome message for the user
- **Parameters**:
  - `name` (string): Name of the user to welcome

## Development

### Project Structure

```text
├── main.py          # Main MCP server implementation
├── pyproject.toml   # Project dependencies and metadata
├── uv.lock         # Locked dependencies
├── uv.toml         # UV configuration
├── README.md       # This file
└── LICENSE         # License file
```

### Adding New Tools

To add a new tool to the MCP server:

1. Define your tool function in `main.py`:

   ```python
   @mcp.tool(
       title="Your Tool Name",
       description="Description of what your tool does",
   )
   def your_tool_name(
       param1: str = Field(description="Description of parameter")
   ) -> str:
       # Your tool logic here
       return "Result"
   ```

2. Restart the server to load the new tool

## Configuration

The server can be configured by modifying the FastMCP initialization in `main.py`:

- `host`: Server host (default: "0.0.0.0")
- `port`: Server port (default: 3000)
- `debug`: Enable debug mode (default: False)
- `stateless_http`: Enable stateless HTTP mode (default: True)

## Troubleshooting

### Common Issues

1. **Connection Error**: If you get "TypeError: fetch failed" errors, ensure:

   - The server is running (`uv run python main.py`)
   - The URL in your MCP config uses `http://` not `https://`
   - The port matches (default is 3000)

2. **Tool Not Found**: If tools aren't appearing:
   - Check that the server started without errors
   - Verify the MCP client configuration
   - Restart both the server and the MCP client

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the terms specified in the LICENSE file.

## Links

- [FastMCP Documentation](https://github.com/jlowin/fastmcp)
- [Model Context Protocol Specification](https://modelcontextprotocol.io/)
- [VS Code MCP Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-mcp)
