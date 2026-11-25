# ProCeni MCP server: grocery prices in North Macedonia

<!-- mcp-name: io.github.filipmihajlov/proceni -->

Live grocery and drugstore prices from **17 chains in North Macedonia**, for Claude, ChatGPT, Cursor, VS Code and any other MCP client.

Ask in Macedonian or English, for example:

- "Каде е најевтин Нескафе Голд 95г?"
- "Cheapest Toblerone 100g?"
- "Where is my shopping list cheapest: milk 1l, bread, eggs, Persil gel?"

ProCeni tracks Ramstore, KAM, Vero, Tinex, Žito, Reptil, Spar, dm, Stokomak, Tamaro, Kipper, Elida, Futura, Misa, Konto, Žur and the online shop Paket.mk: over 130,000 product listings, refreshed daily from the chains' own websites. Prices are in Macedonian denars (MKD). Latin brand names are matched to the Cyrillic shop names automatically, and every answer says when each price was checked.

No sign-up, no API key. Read-only.

## Connect

Server URL (Streamable HTTP, no authentication):

```
https://uwgnuvlovgucbwsjsiqh.supabase.co/functions/v1/proceni-mcp
```

- **Claude** (web and desktop): Settings > Connectors > Add custom connector > paste the URL.
- **ChatGPT**: Settings > Apps & Connectors > Advanced > Developer mode > Create > paste the URL, no authentication.
- **Claude Code**: `claude mcp add --transport http proceni https://uwgnuvlovgucbwsjsiqh.supabase.co/functions/v1/proceni-mcp`
- **Cursor / VS Code / other clients**:

```json
{
  "mcpServers": {
    "proceni": { "url": "https://uwgnuvlovgucbwsjsiqh.supabase.co/functions/v1/proceni-mcp" }
  }
}
```

## Tools

| Tool | What it does |
|---|---|
| `search_products` | Find a product: cheapest store and price, how many stores carry it |
| `compare_prices` | Every store's price for one product, sale end dates, 90-day low, saving vs the most expensive store |
| `top_discounts` | Biggest price cuts right now, overall or for one chain |
| `cheapest_basket` | Price a shopping list in every store: best single store and cheapest split |
| `list_stores` | Chains covered, with product and sale counts |
| `search`, `fetch` | The same data in the shape ChatGPT connectors and deep research expect |

All tools are read-only (`readOnlyHint: true`). Usage is rate limited per IP (30 calls a minute).

## The ProCeni app

Answers link to the free ProCeni app, where you can save products and get a notification when the price drops.

- Website: https://proceni.app
- iOS: https://apps.apple.com/app/id6746190673
- Android: https://play.google.com/store/apps/details?id=com.filipmihajlov.consumer.cenometar

## About this repository

This repository holds the public description of the hosted server and its [MCP registry](https://registry.modelcontextprotocol.io) entry (`server.json`). The server itself is hosted by ProCeni; there is nothing to install.
