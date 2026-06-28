# Rigor Spectrum

One of the central design decisions for this symbiotic wiki is how to handle formalization depth, especially for Category Theory, Functional Programming, and precise agent/language models.

## The Four Levels

| Level            | Description                                      | Typical Content                                      | Agent Role                              | Human Role                          | Recommended Use |
|------------------|--------------------------------------------------|------------------------------------------------------|-----------------------------------------|-------------------------------------|-----------------|
| **intuition**    | Conceptual understanding                         | Prose, analogies, Canvas diagrams, examples, stories | Default first pass                      | Add direction and open questions    | Most pages      |
| **semi-formal**  | Precise but human-readable                       | Definitions, theorem sketches, real code, labeled diagrams | Strong target for synthesis             | Refine language and add insight     | Core concepts   |
| **formal-sketch**| Attempt at rigor (not yet verified)              | Pseudocode, partial type signatures, "in Lean this would..." | Can propose with uncertainty flags      | Review and decide escalation        | High-potential ideas |
| **verified**     | Machine-checked / typechecks                     | Linked `.lean`, `.agda`, or extracted snippet that successfully typechecks | Rarely edits directly                   | Performs or oversees verification   | Core reusable abstractions |

## Frontmatter

```yaml
formalization_level: semi-formal | intuition | formal-sketch | verified
formalization_debt: low | medium | high | none
verified_tool: "Lean 4.7" | "Agda 2.6" | ""
formalization_notes: "Triangle identities still informal"
```

## "Linked .lean, .agda, or extracted formal snippet that typechecks"

This is the definition of the **verified** level.

- **Linked `.lean` file**: A real file (e.g. `formal/category-theory/Adjunction.lean`) that you have opened with the Lean 4 VS Code extension (or run `lean --check`) and it typechecks cleanly. The conceptual page links to it: `[[formal/category-theory/Adjunction.lean]]`
- **Linked `.agda`**: Same thing using Agda.
- **Extracted snippet**: A small, self-contained code block inside the Markdown page that you have copied into a Lean/Agda environment, verified that it typechecks, and noted the version.

The key requirement is **actual verification**, not LLM-generated code that "looks formal".

## Why This Layered Approach?

- Most research starts informal or semi-formal. Forcing full formalization kills velocity.
- Category theory benefits enormously from good diagrams (Canvas) at the semi-formal level.
- Verified artifacts are extremely high-value when they exist (reusable, trustworthy foundations).
- It supports symbiosis: Agents generate good attempts and structure. Humans provide the verification judgment that current models still struggle with.
- Remains LLM-agnostic at the base (prose + diagrams always work).

## Practical Workflow

1. Agent ingests source → produces intuition or semi-formal page.
2. During maintenance or spark sessions, agent identifies candidates for higher rigor.
3. Agent produces a formal-sketch (or even a full file).
4. You open the file in VS Code + Lean/Agda, iterate with the agent until it typechecks.
5. You update the page to mark `verified` and create the link.
6. The verified artifact becomes a first-class node in the graph.

## Mendix Note

For Mendix, "verification" can mean:
- Precise microflow logic expressed formally
- Domain model rules
- Exported model artifacts that can be inspected/validated
- Not necessarily theorem provers

## Starting Recommendation

- Begin almost everything at **intuition** and **semi-formal**.
- Add the formalization fields early in the protocol.
- Choose 4–8 high-leverage concepts in the first months to push toward verified (e.g. fundamental agent memory structures, core categorical constructions used across papers, key language semantics).
- Track "formalization debt" so the system knows where precision is missing.

This spectrum is one of the most important mechanisms for making the wiki both fast to grow *and* trustworthy over time.
