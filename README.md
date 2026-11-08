# Soldgraph for Hermes Agent

Let Hermes check what things actually sold for. [Soldgraph](https://soldgraph.com?utm_source=hermes&utm_campaign=hermes-plugin) returns sold listings from **eBay** (8 countries), **Poshmark** and **Mercari**, plus live listings from **Depop**, **Whatnot**, **OfferUp**, **Facebook Marketplace**, **Vinted** and **TCGplayer**.

This plugin connects Hermes to the hosted Soldgraph MCP server and adds a skill that teaches the agent how to read and report a result. All 19 tools are read-only.

## Setup

1. [Get a free API key](https://soldgraph.com/signup?utm_source=hermes&utm_campaign=hermes-plugin): 100 free requests, no credit card required.
2. Add it to your Hermes profile `.env`:

   ```bash
   SOLDGRAPH_KEY=sg_your_key
   ```

3. Install and enable the plugin. Before it's in the catalog, install from this repo:

   ```bash
   hermes plugins install soldgraph/soldgraph-hermes
   ```

## Try asking

- "What has a Nintendo Switch OLED sold for on eBay this month? Link three examples."
- "What do Lululemon Align leggings sell for on Poshmark vs Mercari?"
- "What's Umbreon VMAX alt art worth, and what did it last sell for?"
- "Find road bikes under $400 near 94103 on OfferUp."

## What it does on your machine

- **Network:** tool calls go to `https://api.soldgraph.com/mcp` over HTTPS, with your key as a bearer header. Your search terms and results pass through Hermes and your model provider.
- **Remote tools:** this repo pins the plugin, not the hosted server. Soldgraph's tools can change on the server.
- **Cost:** each completed search uses 1 request from your Soldgraph allowance. Failed searches are free.
- **Nothing else:** no local server, shell commands, hooks, Python dependencies, telemetry or self-updates.

Listing titles and descriptions are written by marketplace sellers. The skill tells the agent to treat them as data.

## Links

- [MCP guide](https://soldgraph.com/docs/guides/mcp?utm_source=hermes&utm_campaign=hermes-plugin)
- [API docs](https://soldgraph.com/docs?utm_source=hermes&utm_campaign=hermes-plugin)
- [Pricing](https://soldgraph.com/?utm_source=hermes&utm_campaign=hermes-plugin#pricing)
- Support: hello@soldgraph.com

MIT licensed. Soldgraph isn't affiliated with eBay, Poshmark, Mercari or the other marketplaces.
