# MCP Exercise Project

This repository contains Python files demonstrating Model Context Protocol (MCP) server implementation and directory listing utilities.

## Files Overview

### 1. `my_mcp_server.py`
**Main MCP Server Implementation**

This is the core MCP server built using the FastMCP framework. It provides several tools accessible through the Model Context Protocol:

**Features:**
- **say_hello(name)**: A simple greeting function that welcomes users
- **list_directory(directory_path)**: Basic directory listing functionality with error handling
- **list_details(directory_path)**: Advanced directory listing with file details including:
  - File/directory name
  - Size in bytes
  - Type (file or directory)
  - Last modified timestamp
- **get_weather(location)**: Weather fetching tool that uses the wttr.in API to get current weather for any city or country

**Dependencies:**
- `mcp.server.fastmcp` - FastMCP framework
- `mcp.server.stdio` - Standard I/O transport
- `mcp.types` - MCP type definitions
- `pathlib` - Modern file path handling
- `datetime` - Timestamp formatting
- `requests` - HTTP requests for weather API
- `os` - Operating system interface

**Usage:**
Run the server with: `python my_mcp_server.py`
The server starts with stdio transport for MCP communication.

### 2. `adv_list_dir.py`
**Advanced Directory Listing Utility**

A standalone script that provides detailed directory information using modern Python practices.

**Features:**
- Uses `pathlib.Path` for modern file handling
- Returns comprehensive file details:
  - File name
  - File size in bytes
  - File type (file or directory)
  - Last modified date and time
- Proper error handling for non-existent paths and non-directories
- Interactive command-line interface

**Key Advantages:**
- More Pythonic approach using `pathlib`
- Better timestamp formatting
- Structured data output as dictionaries

### 3. `basic_list_dir.py`
**Basic Directory Listing Utility**

A simple directory listing script using traditional Python `os` module.

**Features:**
- Basic file listing using `os.listdir()`
- Error handling for:
  - FileNotFoundError (directory doesn't exist)
  - PermissionError (access denied)
- Simple command-line interface
- Returns list of file/directory names only

**Use Case:**
Ideal for simple directory listing when detailed file information is not needed.

## Comparison: Basic vs Advanced Directory Listing

| Feature | basic_list_dir.py | adv_list_dir.py |
|---------|-------------------|-----------------|
| **Module Used** | `os` | `pathlib` |
| **Output** | List of names only | Detailed file information |
| **Error Handling** | Basic (found/permission) | Comprehensive path validation |
| **Data Structure** | Simple list | List of dictionaries |
| **Timestamps** | No | Yes (formatted) |
| **File Size** | No | Yes |
| **File Type** | No | Yes (file/directory) |
| **Python Style** | Traditional | Modern/Pythonic |

## Getting Started

1. **Install Dependencies:**
   ```bash
   pip install mcp requests
   ```

2. **Run the MCP Server:**
   ```bash
   python my_mcp_server.py
   ```

3. **Test Directory Utilities:**
   ```bash
   python basic_list_dir.py
   python adv_list_dir.py
   ```

## MCP Tools Available

When the MCP server is running, the following tools are available for use:

1. **say_hello** - Greeting functionality
2. **list_directory** - Basic directory listing
3. **list_details** - Advanced directory information
4. **get_weather** - Current weather information

## Example Usage

### Weather Query:
```python
# Through MCP: get_weather("Sydney")
# Returns: "Sydney: 🌧   +12°C"
```

### Directory Listing:
```python
# Basic listing
list_directory("C:\\Users")
# Returns: ['23042538', 'All Users', 'Default', ...]

# Detailed listing  
list_details("C:\\Users")
# Returns: [{'name': '23042538', 'size': 24576, 'type': 'directory', 'last_modified': '2025-07-08 18:35:03'}, ...]
```

## Project Structure
```
mcp-exercise/
├── my_mcp_server.py      # Main MCP server implementation
├── adv_list_dir.py       # Advanced directory utility
├── basic_list_dir.py     # Basic directory utility
└── README.md             # This documentation
```

## Notes
- The MCP server uses stdio transport for communication
- Weather data is fetched from wttr.in API
- All directory utilities include proper error handling
- The project demonstrates both traditional and modern Python file handling approaches