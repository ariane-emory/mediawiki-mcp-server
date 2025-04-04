# MediaWiki MCP Server 🚀

A powerful MediaWiki Multi-Call Protocol (MCP) server that provides seamless interaction with Wikipedia's API. This tool allows you to search and retrieve Wikipedia content programmatically! 📚

## Features ✨

- 🔍 Search Wikipedia pages with customizable result limits
- 📖 Retrieve detailed page content
- 🌐 Configurable base URL support, support basically any wiki site using MediaWiki. (e.g. Game Wiki)

## Configuration 🔧

The server can be configured through environment variables and command-line arguments:

- **HTTP Proxy** (Optional): Set via environment variable

```bash
export HTTP_PROXY="http://your-proxy-server:port"
```

- **Base URL**: Default is "<https://en.wikipedia.org/w/>", can be modified via command-line argument

## Usage 💻

1. Ensure that uv is installed on your device.
2. Clone this repo and execute:

```bash
uv sync
```

3.

Command:

```bash
uv
```

Args:

```bash
run
--directory
<path-to-server>src/mediawiki_mcp_server
mediawiki-mcp-server
--base-url
<mediawiki-site-you-want>
```

Envs:

```bash
HTTP_PROXY=http://host:port
```

## Supported Tools 🛠

### Search

```python
async def search(query: str, limit: int = 5)
```

- `query`: Search term (preferably short and focused)
- `limit`: Maximum number of results to return (default: 5)

### Get Page

```python
async def get_page(title: str)
```

- `title`: The exact title of the Wikipedia page to retrieve

## Contributing 🤝

This server is under development. Contributions are welcome! Feel free to submit issues and pull requests.
