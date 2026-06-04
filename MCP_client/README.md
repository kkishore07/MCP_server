# MCP Client

This client connects to an MCP server over stdio, discovers available tools, and lets Claude call them during an interactive chat session.

## Requirements

- Python 3.13 or newer
- `uv`
- An Anthropic API key

## Setup

1. Create a `.env` file in this folder with your API key:

	```env
	ANTHROPIC_API_KEY=your-api-key-here
	```

2. Install dependencies:

	```bash
	uv sync
	```

## Run

Start the client by pointing it at the MCP server script:

```bash
uv run python client.py ..\MCP_server\main.py
```

The client will connect to the server, list the available tools, and then open an interactive prompt.

## Usage

- Type a query and press Enter.
- Type `quit` to exit.
- If `ANTHROPIC_API_KEY` is missing, the client will connect to the server but stop before starting chat mode.

## Server Notes

The bundled server exposes a weather tool through `main.py` and runs with stdio transport.
