# CLAUDE.md — Second Brain Schema

This file tells Claude Code how to operate on this Obsidian vault. It is the schema layer of the LLM Wiki pattern.

## Architecture

This vault has three layers:

- **`raw/`** — Immutable source documents (articles, papers, clippings). Claude reads but NEVER modifies these. `raw/assets/` stores downloaded images and attachments.
- **`wiki/`** — LLM-generated and maintained markdown pages. Summaries, entity pages, concept pages, comparisons, synthesis. Claude owns this layer entirely.
- **`sources/`** — One summary page per ingested source, with metadata and key takeaways.

## Special Files

- **`index.md`** — Content catalog of everything in the wiki. Each page listed with a link, one-line summary, and category. Updated on every ingest. Read this first when answering queries.
- **`log.md`** — Append-only chronological record. Each entry: `## [YYYY-MM-DD] action | Title`. Actions: `ingest`, `query`, `lint`, `update`.

## Workflows

### Ingest

When the user adds a new source to `raw/` or asks to process content:

1. Read the source material thoroughly
2. Discuss key takeaways with the user
3. Create a summary page in `sources/` with YAML frontmatter:
   ```yaml
   ---
   title: "Source Title"
   author: "Author Name"
   date_ingested: YYYY-MM-DD
   date_published: YYYY-MM-DD
   tags: [tag1, tag2]
   url: "original URL if applicable"
   ---
   ```
4. Create or update relevant pages in `wiki/` — entity pages, concept pages, topic pages
5. Update `index.md` with new/changed pages
6. Append an entry to `log.md`

A single source may touch 10-15 wiki pages. Always maintain cross-references using `[[wikilinks]]`.

### Query

When the user asks a question:

1. Read `index.md` to find relevant pages
2. Read those pages and synthesize an answer
3. If the answer is valuable and reusable, offer to save it as a new wiki page
4. Append a query entry to `log.md`

### Lint

When asked to health-check the wiki:

- Find contradictions between pages
- Identify stale claims superseded by newer sources
- Find orphan pages with no inbound links
- Spot important concepts mentioned but lacking their own page
- Check for missing cross-references
- Suggest new questions to investigate or sources to seek

## Conventions

- All wiki pages use `[[wikilinks]]` for internal links
- Tags in frontmatter use lowercase, hyphenated format: `[machine-learning, crypto]`
- Page filenames use kebab-case: `bitcoin-etf-analysis.md`
- Every wiki page should have YAML frontmatter with at least: `title`, `tags`, `date_created`, `date_modified`
- When new information contradicts existing pages, flag the contradiction explicitly and update both pages
- Prefer updating existing pages over creating new ones when the topic overlaps

## Wiki Page Template

```markdown
---
title: "Page Title"
tags: [tag1, tag2]
date_created: YYYY-MM-DD
date_modified: YYYY-MM-DD
related: ["[[Related Page 1]]", "[[Related Page 2]]"]
---

# Page Title

Content here. Use [[wikilinks]] to connect to other pages.

## References

- Sources that informed this page
```
