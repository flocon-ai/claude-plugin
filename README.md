# Flocon AI plugin for Claude

Publish SEO pages to your own website, straight from Claude.

[Flocon AI](https://flocon-ai.com) stores your pages. Your Next.js, React or Astro website shows them with one npm package. This plugin connects Claude to the Flocon AI MCP server and adds a skill that helps Claude write useful, unique pages.

## What you get

- **The Flocon AI MCP server:** create, update, publish, schedule and delete pages on your website. Tools: `get_website`, `list_pages`, `search_pages`, `get_page`, `create_page`, `update_page`, `publish_page`, `unpublish_page`, `delete_page`, `get_setup`, `list_docs`, `read_doc`.
- **The `write-seo-pages` skill:** answer-first pages, real facts only, comparison tables, FAQ, tight SEO fields, and one page a day for big batches.

## Before you start

1. Create a free website at [flocon-ai.com](https://flocon-ai.com).
2. Add the Flocon AI package to your website: [Next.js](https://flocon-ai.com/docs/nextjs/install), [React](https://flocon-ai.com/docs/react/install) or [Astro](https://flocon-ai.com/docs/astro/install). Your AI can also call `get_setup` for ready-to-paste code.
3. Copy your **MCP token** from [flocon-ai.com/app/tokens](https://flocon-ai.com/app/tokens). One token = one website.

## Install in Claude Code

```bash
/plugin marketplace add flocon-ai/claude-plugin
/plugin install flocon-ai@flocon-ai
```

Claude Code asks for your MCP token when you enable the plugin. It is stored as a secret, not in a plain config file.

Then try:

```text
Write a page at /vs/notion on my Flocon AI website.
Compare my product with Notion. Add a comparison table and a FAQ.
```

## What this plugin sends, and where

- It talks to **one** server: `https://mcp.flocon-ai.com`, run by Flocon AI.
- It sends your MCP token (in the `Authorization` header) and what Claude writes for your pages: paths, titles, SEO fields and blocks.
- Flocon AI stores your pages to show them on your website. Published pages are public on your website. Drafts stay private.
- The plugin runs no local code, installs no packages and has no hooks.
- Privacy policy: [flocon-ai.com/privacy](https://flocon-ai.com/privacy).

## Plans

Free: 10 published pages. Pro: 50 published pages. Business: 500 published pages. Limits are per website. See [pricing](https://flocon-ai.com/pricing).

## Help

- Docs: [flocon-ai.com/docs](https://flocon-ai.com/docs)
- Example websites: [github.com/flocon-ai/demo](https://github.com/flocon-ai/demo)
- Contact: alfred@flocon-ai.com

## License

[MIT](./LICENSE)
