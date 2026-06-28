# Directory Structure

Recommended layout for the symbiotic Obsidian LLM Wiki.

```
symbiotic-llm-wiki/
├── README.md
├── llm-wiki.md                    # Original Karpathy pattern
├── ARCHITECTURE.md
├── RIGOR-SPECTRUM.md
├── WIKI-PROTOCOL.md               # The main agent contract
├── DIRECTORY-STRUCTURE.md         # This file

├── raw/                           # Immutable source of truth (never edit)
│   ├── inbox/
│   ├── papers/
│   ├── articles/
│   ├── code-examples/
│   ├── mendix/
│   ├── transcripts/
│   └── archive/                   # Successfully processed sources

├── assets/                        # Images, diagrams, attachments

├── wiki/                          # LLM-maintained synthesized layer
│   ├── index.md                   # Master content catalog (read this first)
│   ├── log.md                     # Append-only chronological record
│   ├── concepts/                  # Abstract ideas, patterns
│   ├── theories/                  # Deeper formal-ish treatments
│   ├── entities/                  # Languages, tools, papers, people
│   ├── implementations/           # Concrete code / Mendix realizations
│   ├── syntheses/                 # Filed-back answers and deep reports
│   ├── tensions/                  # Contradictions and open problems
│   ├── maps/                      # Hierarchical MOCs and Canvas diagrams
│   └── meta/                      # Generated reports, coverage

├── formal/                        # Machine-checkable artifacts
│   ├── category-theory/
│   ├── functional-programming/
│   ├── agent-memory/
│   └── mendix/

├── meta/                          # System-level documentation
│   └── architecture/              # (this repo's design docs live here too)

├── .claude/                       # Agent skills (if using Claude Code)
│   └── skills/

└── .obsidian/                     # Obsidian configuration (optional to commit)
```

## Key Design Notes

- `raw/` is the only immutable layer.
- `wiki/` is where the agent has primary write authority.
- `formal/` contains verified `.lean` / `.agda` files (linked from wiki pages).
- Keep `index.md` and `log.md` at the root of `wiki/` for easy access.
- Use Obsidian's attachment settings to point to `assets/`.

This structure supports both rapid growth and high-rigor formal work while remaining pleasant to navigate in Obsidian.
