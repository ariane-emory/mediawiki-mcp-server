# MediaWiki MCP Server 🚀

A MCP server that provides seamless interaction with Wikipedia's API. This tool allows you to search and retrieve Wikipedia content with LLMs 🤖!

<https://github.com/user-attachments/assets/b5d9c5f3-a60e-48ea-8b4b-f1a7524d4fbb>

## Features ✨

- 🔍 Search wiki pages with customizable wiki site. e.g. wikipedia.org, fandom.com, wiki.gg and more!
- 📖 Retrieve detailed page content

## Usage 💻

1. Ensure that uv is installed on your device.
2. Clone this repo and execute:

```bash
uv sync
```

3. Configure in your client:

Command:

```bash
uv
```

Args:

The server defaults to using <https://en.wikipedia.org/>. Also, you can make the server search other wiki sites!

To see if a wiki site works with this server, check if it uses MediaWiki software (usually shown by an icon at the bottom of the site).

To check further and find the endpoint (usually the website's domain, like <https://mediawiki.org/>), check by going to base-url/rest.php/v1/page in a browser (like <https://noita.wiki.gg/rest.php/v1/page>) and see if the output looks right. If not, add '/w' to the base URL and try again.

![](/imgs/PixPin_2025-04-04_19-41-55.png)

Then, set this endpoint as --base-url.

```json
{
    "command": "uvx",
    "args": [
        "mediawiki-mcp-server",
        "--base-url", // if needed
        "https://example.com/" // if needed
    ],
    "env": {
        "HTTP_PROXY": "http://example.com:port" // if needed
    }
}
```

Or, if you want to run this server from source:

```bash
run
--directory
path/to/project/src/mediawiki_mcp_server
mediawiki-mcp-server
--base-url
https://example.com/
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

## Development 👨‍💻

```bash
npx @modelcontextprotocol/inspector uv run mediawiki-mcp-server
```

Here are some documents that might help:

- <https://www.mediawiki.org/api/rest_v1/>

## Contributing 🤝

This server is under development. Contributions are welcome! Feel free to submit issues and pull requests.

## Related Projects ♥️

- [Cherry Studio](https://github.com/CherryHQ/cherry-studio): A desktop client that supports for multiple LLM providers. MCP is supported.
