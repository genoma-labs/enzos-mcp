# Enzo's MCP server

[![Listed on mcpservers.org](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/genoma-labs/enzos-mcp)

Connect any MCP-compatible AI assistant (ChatGPT, Claude, Gemini, and others) to
[Enzo's](https://enzos.ai) live US home-for-sale data.

Enzo's is an AI home-discovery product by GENOMA Labs. This repository documents its public,
hosted **Model Context Protocol (MCP)** server, so your assistant can search real listings and
give grounded, cited answers instead of stale guesses.

- Website: https://enzos.ai
- Connect guide: https://enzos.ai/for-agents
- MCP endpoint (Streamable HTTP): `https://enzos.ai/mcp`

## Tools

| Tool | What it does |
| --- | --- |
| `search_homes` | Search real for-sale homes by plain language, architectural style, features, budget, beds/baths, and location (metro or neighborhood). Returns matching homes with price, style, and a link to the original source listing. |
| `home_verdict` | Enzo's honest, independent read for one listing: how its price compares to similar homes nearby, price per square foot, days on market, and any price cuts. |
| `below_market_deals` | Homes currently priced below comparable homes in a given metro, newest-value first. |

## Connect

The server speaks MCP over Streamable HTTP at `https://enzos.ai/mcp`. Add that URL as a remote
MCP server in any MCP-capable client. Step-by-step instructions for ChatGPT, Claude, and Gemini
are at https://enzos.ai/for-agents.

Quick check (lists the tools):

```bash
curl -s https://enzos.ai/mcp \
  -H 'content-type: application/json' \
  -H 'accept: application/json, text/event-stream' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

## About

Enzo's is built by [GENOMA Labs](https://www.genoma-labs.com). Every home links out to its
original source listing; Enzo's never rehosts.
