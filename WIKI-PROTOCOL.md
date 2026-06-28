# WIKI-PROTOCOL.md

This is the core contract / schema for the symbiotic LLM Wiki.

It is written to be as LLM-agnostic as possible while being actionable for capable agents (Claude Code, Codex, OpenCode, Cursor, etc.).

## Foundational Rules

1. **Raw sources are immutable.** Never modify files in `raw/`. Move to `raw/archive/` only after successful processing.
2. **The LLM owns the wiki layer.** You read and steer. The agent creates, updates, cross-references, and maintains.
3. **Symbiosis over automation.** Prioritize co-evolution. Make it easy for the human to inject judgment and for the agent to propose structure.
4. **Provenance and voice matter.** Distinguish Human Insight from Agent Synthesis.
5. **Structure is the goal.** Favor explicit relations, especially category-theoretic ones.

## Page Types (use in frontmatter)

- `type: theory | concept | construction | implementation | pattern | mendix-artifact | agent-trace | counterexample | tension | map | synthesis`

## Required / Recommended Frontmatter

```yaml
type: concept
sources: ["[[raw/papers/some-paper.md]]"]
formalization_level: semi-formal
formalization_debt: medium
relations:
  - morphism: "[[FreeMonad]]"
  - functor_from: "[[CategoryOfEffects]]"
tags: [category-theory, monads, agent-memory]
last_updated: 2026-06-28
confidence: high
```

## Attribution Conventions

In pages use clear sections:

```markdown
## Human Insight

> Your thoughts, taste, open questions...

## Agent Synthesis

> Agent-generated connections and summaries...

## Formalization

Status and links.
```

## Operations

### Ingest
- Read the new raw source.
- Perform **structural analysis**: identify key objects, morphisms, universal properties, analogies to existing wiki content.
- Update or create:
  - One source summary page
  - Relevant entity / concept / pattern pages
  - Cross-links (especially CT-style relations)
  - Update `wiki/index.md`
  - Append to `wiki/log.md` with consistent prefix: `## [YYYY-MM-DD] ingest | Title`

A single source should typically touch 5–15 wiki pages.

### Query / Synthesis
- Read `wiki/index.md` first (or use local search).
- Navigate the graph looking for structural relationships.
- Produce answers that can themselves become first-class wiki pages (especially in `wiki/syntheses/`).
- File good outputs back into the wiki.

### Maintenance & Lint
- Check for orphans, broken links, missing concepts, stale claims.
- Track contradictions / tensions explicitly.
- Run subgraph-focused checks for efficiency.
- Propose refinements and new questions.

### Rigor Handling
See [RIGOR-SPECTRUM.md](RIGOR-SPECTRUM.md)

Agents should default to intuition or semi-formal unless the concept is highly connected and foundational.

## Special Files

- `wiki/index.md` — Content-oriented catalog. Read this first when answering questions.
- `wiki/log.md` — Chronological, grep-friendly record. Use consistent `## [date] action | title` format.

## Agent Skills Expectations

Base on kepano/obsidian-skills (markdown, canvas, bases, cli).

Additional recommended domain skills:
- categorify
- extract-morphisms
- find-isomorphisms
- map-to-mendix
- propose-formalization

## Human Steering Mechanisms

- Add high-signal notes with `## Human Insight`
- Create explicit question pages
- Mark pages with `formalization_debt` or `confidence`
- Perform certification of verified formal artifacts

## LLM Agnosticism

- Core behavior is documented in clear, example-heavy language.
- Prefer structured output (frontmatter, consistent headings).
- Use open Agent Skills spec for file operations.
- The vault itself (files + graph) is the portable artifact.

## Evolution

This protocol is expected to co-evolve. When the wiki grows or new patterns emerge, update this file and note the change in the log.

---

This protocol turns a generic LLM into a disciplined maintainer of a structural, symbiotic knowledge base.
