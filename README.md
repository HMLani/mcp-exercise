# MCP Exercise Project 🚀

Welcome! 👋 This repository contains Python files demonstrating Model Context Protocol (MCP) server implementation and directory listing utilities. It's a practical exploration of MCP capabilities with some handy tools thrown in! 🐍

## Project Overview 📦

### 1. `my_mcp_server.py` 🌟
**Main MCP Server Implementation**

This is the core MCP server built using the FastMCP framework. It provides several useful tools accessible through the Model Context Protocol:

**Features:**
- **say_hello(name)** 👋: A friendly greeting function for user interaction
- **list_directory(directory_path)** 📁: Basic directory listing with comprehensive error handling
- **list_details(directory_path)** 🔍: Advanced directory listing with detailed file information:
  - File/directory names
  - File sizes in bytes
  - File type identification (file or directory)
  - Last modified timestamps
- **get_weather(location)** 🌤️: Weather fetching tool using the wttr.in API for current weather data

**Dependencies:**
- `mcp.server.fastmcp` - FastMCP framework for server implementation
- `mcp.server.stdio` - Standard I/O transport layer
- `mcp.types` - MCP type definitions
- `pathlib` - Modern file path handling ✨
- `datetime` - Timestamp formatting utilities 🕐
- `requests` - HTTP requests for weather API integration
- `os` - Operating system interface

**Usage:**
Run the server with: `python my_mcp_server.py`
The server initializes with stdio transport for MCP communication.

### 2. `adv_list_dir.py` 🚀
**Advanced Directory Listing Utility**

A sophisticated standalone script that provides detailed directory information using modern Python practices.

**Key Features:**
- Uses `pathlib.Path` for modern, Pythonic file handling
- Returns comprehensive file details including:
  - File names and paths
  - File sizes in bytes
  - File type classification (file or directory)
  - Formatted last modified timestamps
- Robust error handling for non-existent paths and access issues 🛡️
- Interactive command-line interface for easy use

**Advantages:**
- Modern Python approach with `pathlib` (clean and readable code ❤️)
- Human-readable timestamp formatting
- Well-structured data output as dictionaries

### 3. `basic_list_dir.py` 📝
**Simple Directory Listing Utility**

A straightforward directory listing script using the traditional Python `os` module - perfect for basic file exploration.

**Features:**
- Simple file listing using `os.listdir()`
- Handles common error scenarios:
  - FileNotFoundError (directory doesn't exist) 🤷‍♀️
  - PermissionError (access denied) 🚫
- Clean command-line interface
- Returns a simple list of file/directory names

**Best Use Case:**
Ideal for quick directory contents overview when detailed file information isn't required.

## Feature Comparison 📊

| Feature | basic_list_dir.py | adv_list_dir.py |
|---------|-------------------|-----------------|
| **Module Used** 🔧 | `os` (traditional) | `pathlib` (modern) |
| **Output Format** 📤 | Simple list | Detailed information |
| **Error Handling** 🛡️ | Basic validation | Comprehensive checks |
| **Data Structure** 📊 | List of strings | List of dictionaries |
| **Timestamps** ⏰ | Not included | Formatted timestamps |
| **File Sizes** 📏 | Not provided | Full size information |
| **Type Detection** 🏷️ | Not available | File/directory classification |
| **Code Style** 🐍 | Traditional approach | Modern Python practices |

## Getting Started 🚀

### Installation
```bash
pip install mcp requests
```

### Running the Applications

1. **Start the MCP Server:**
   ```bash
   python my_mcp_server.py
   ```

2. **Test Directory Utilities:**
   ```bash
   python basic_list_dir.py
   python adv_list_dir.py
   ```

## Available MCP Tools 🧰

When the MCP server is running, these tools are available for use:

1. **say_hello** 👋 - User greeting functionality
2. **list_directory** 📁 - Basic directory listing
3. **list_details** 🔍 - Comprehensive directory analysis
4. **get_weather** 🌦️ - Current weather information retrieval

## Usage Examples 💡

### Weather Information:
```python
# Using MCP tool: get_weather("Sydney")
# Returns: "Sydney: 🌧   +12°C"
# Perfect for checking conditions before heading out! ☂️
```

### Directory Operations:
```python
# Basic directory listing
list_directory("C:\\Users")
# Returns: ['23042538', 'All Users', 'Default', ...]

# Detailed directory analysis
list_details("C:\\Users")
# Returns: [{'name': '23042538', 'size': 24576, 'type': 'directory', 'last_modified': '2025-07-08 18:35:03'}, ...]
```

## Project Structure 📁
```
mcp-exercise/
├── my_mcp_server.py      # Main MCP server implementation ⭐
├── adv_list_dir.py       # Advanced directory utility 🔍
├── basic_list_dir.py     # Simple directory listing �
└── README.md             # Project documentation �
```

## Technical Notes 📝
- The MCP server uses stdio transport for client-server communication 💬
- Weather data is sourced from the reliable wttr.in API 🌐
- All utilities include proper error handling for robust operation 💪
- The project demonstrates both traditional and modern Python file handling approaches 🐍

Enjoy exploring the MCP capabilities and happy coding! ✨