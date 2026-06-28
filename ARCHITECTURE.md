# Architecture

This document captures the architectural thinking for a symbiotic LLM Wiki implemented in Obsidian.

## Core Principles (Symbiosis First)

- The wiki is a **shared external mind**, not a tool the LLM controls or the human fully manages.
- Human strengths: taste, semantic grounding, high-level direction, verification.
- System strengths: breadth, recall, cross-domain connection, consistent bookkeeping, formalization attempts.
- Co-evolution: Using the system improves your thinking; your interventions improve the system's quality.
- LLM-agnostic core: Plain files, wikilinks, Canvas, frontmatter, and clear protocols are the durable layer.

## Layered Architecture

### 1. Substrate Layer
- Plain Markdown + YAML frontmatter + wikilinks + JSON Canvas
- Git repository (version history, branching for exploration)
- Fully portable and future-proof

### 2. Representation Layer (Domain-Optimized)
Tailored to Category Theory, FP, languages, agentic systems, and Mendix.

**Primary Page Types:**
- Theory / Concept
- Construction / Formalism
- Implementation / Realization
- Pattern
- MendixArtifact
- AgentTrace / Episode
- Counterexample, OpenQuestion, Tension
- Isomorphism / Correspondence

**Relations (as wikilinks + structured sections):**
- Classic CT vocabulary: morphism, functor, natural transformation, adjunction, monad, dual, limit/colimit...
- Practical: implements, generalizes, refines, analogous in Mendix via..., used in agent architecture...

Canvas is used heavily for diagrams (commutative diagrams, agent architectures, language comparisons).

### 3. Protocol / Schema Layer (WIKI-PROTOCOL.md)
The contract that turns generic agents into disciplined wiki maintainers.

- Written to be as LLM-agnostic as possible
- Uses the open Agent Skills specification where possible
- Defines page types, relations, attribution, ingest/query/lint behaviors
- Evolves over time

### 4. Manipulation / Agency Layer
- Base skills: kepano/obsidian-skills (markdown, canvas, bases, cli, defuddle)
- Custom domain skills: "categorify", "extract-morphisms", "map-to-mendix", etc.
- MCP servers for search, graph operations, and external capabilities
- Multiple agents can use the same vault

### 5. Human Interface Layer
- Obsidian (graph view, Canvas, Dataview/Bases, Git plugin)
- Git for branching and review of agent changes

### 6. Augmentation & Reflection Layer
- index.md + log.md (from original pattern)
- Lint, drift detection, confidence tracking
- Meta-synthesis (the system reflects on its own structure)
- Optional formal tool integration (Lean, etc.)

## Operations (Symbiotic Version)

**Ingest** → Structural analysis and relational mapping (not just summarization)

**Query / Synthesis** → Structural exploration ("find the adjunction", "what are the free/forgetful functors here?")

**Maintenance** → Refinement passes + tension tracking

**Human Steering** → High-signal notes, explicit questions, and certification of rigor levels

## Key Differentiators from Basic LLM Wiki

- Strong emphasis on **relations and structure** (category-theoretic thinking)
- Explicit **rigor spectrum** with verified formal artifacts
- **Provenance and voice** (Human vs Agent contributions)
- Designed for **co-evolution** rather than one-way maintenance
- Multi-level abstraction support
- Self-referential capability (the wiki studies agentic memory while being one)

## Open Architectural Questions

See GitHub Issues for current discussions.

This architecture is documented here so it can be read interactively in Obsidian (backlinks, graph, Canvas) and evolved on GitHub.
