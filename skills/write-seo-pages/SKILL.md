---
name: write-seo-pages
description: Plan, write and publish SEO pages on the user's website with the Flocon AI MCP tools. Use when the user asks for a new page, a batch of pages, a comparison (/vs/), alternatives, integrations or use-case pages, or to schedule pages on their Flocon AI website.
---

# Write SEO pages with Flocon AI

Flocon AI stores the pages of one website. The user's website shows them with `@flocon-ai/next`, `@flocon-ai/react` or `@flocon-ai/astro`. You write the pages with the Flocon AI MCP tools.

## Before you write

1. Call `get_website`. Note the locales, the plan, the published limit and the counts.
2. Call `list_pages` or `search_pages`. Don't create a page that already exists. Pick a new angle, or use `update_page`.
3. Ask the user for the facts you don't have: prices, features, numbers, dates. **Never invent facts.**

## What a good page looks like

- **One page = one real question.** The title is that question or its answer.
- **First block: `description`.** Answer the question in 2 to 3 sentences, with the key fact.
- **Unique data on every page.** Not the same text with a new name.
- **A `table`** when you compare things (features, prices, limits).
- **A `faq`** with real questions people ask.
- **A `related` block** that links pages on the same topic. Link only to paths that exist.
- **SEO fields:** `seo.title` 60 characters or less, and `seo.description` 140 to 160 characters. If the tool returns a warning, fix it.
- Text is inline Markdown only (bold, italic, code, links). Headings, lists and tables are blocks.
- No keyword stuffing. Write for people.

## Common paths

| Path | Use it for | Structure |
| --- | --- | --- |
| `/alternatives/<name>` | People leaving a product | description, table, who should switch, faq, related |
| `/vs/<a>-vs-<b>` | A head-to-head comparison | description (the verdict), fair table, which one fits which case, faq |
| `/integrations/<name>` | How the product works with another one | description, setup steps, what is supported, faq |
| `/use-cases/<name>` | How one type of customer uses the product | description, a real example, features that matter, faq, related |

Paths use lowercase letters, digits and dashes, with no locale prefix and no trailing slash. `/` is the homepage.

## Many pages: release them slowly

Don't publish many pages on one day. It looks unnatural to Google.

- Write the batch now and give each page its own `publishAt` date, for example one page a day.
- A scheduled page uses a published slot right away. Check the limit with `get_website` first.
- To review before publishing, create the pages as drafts (`publish: false`), then use `publish_page`.

## After you write

Tell the user, for each page: its path, its status (published, scheduled with the date, or draft) and any warning the tool returned.

Questions about Flocon AI itself (plans, setup, blocks): call `list_docs`, then `read_doc`. Don't guess.
