# Adjunction

**type:** theory  
**formalization_level:** semi-formal  
**formalization_debt:** low

## Human Insight

Adjunctions are one of the most powerful and unifying concepts in category theory. They capture the idea of "free" constructions and their "forgetful" counterparts in a precise, universal way. In the context of this symbiotic LLM Wiki, adjunctions feel particularly natural: the LLM often performs a kind of "free generation" of structure (creating linked wiki pages, syntheses, and cross-references) while the human performs a more "forgetful" or grounding role (reading raw sources, providing intuition, verifying rigor).

Understanding adjunctions helps us see patterns across functional programming, agent architectures, and even how knowledge itself is built and maintained.

## Definition (Semi-Formal)

An **adjunction** between two categories **C** and **D** consists of two functors:

- **F: C → D** (the left adjoint, often the "free" functor)
- **G: D → C** (the right adjoint, often the "forgetful" functor)

Together with two natural transformations:

- **unit**: 𝟭_C → G ∘ F
- **counit**: F ∘ G → 𝟭_D

satisfying the **triangle identities**.

Equivalently, for every object X in C and Y in D there is a natural bijection:

Hom_D(F(X), Y) ≅ Hom_C(X, G(Y))

This says that "maps out of the free thing" correspond to "maps into the forgetful thing."

## Universal Property

The left adjoint F is the "freest" way to construct something in D from something in C. The right adjoint G "forgets" structure.

Classic example in programming:
- F = Free Monoid (or Free Monad)
- G = Forgetful functor from Monoids back to Sets (or underlying type)

## Examples Relevant to This Project

### 1. Functional Programming
- Free Monad ↔ Forgetful functor from monadic computations to plain types.
- This pattern appears constantly when moving between "pure" data and "effectful" computations.

### 2. Agentic AI & Memory
Many agent memory systems can be viewed through adjunctions:
- The "free generation" of memory structures (the LLM creating linked wiki pages, summaries, and relations) vs the "forgetful" reading of raw sources.
- Planning as left adjoint to execution.

### 3. Knowledge Representation (This Wiki)
- **Free construction**: The LLM freely generates a dense network of wikilinks, entity pages, and syntheses from raw sources.
- **Forgetful functor**: Reading the original raw documents or a more grounded view of the same knowledge.
- The unit of the adjunction corresponds to "embedding" a raw source into the richer wiki structure.
- The counit corresponds to "projecting" synthesized knowledge back down to its essential claims.

This is why the original Karpathy pattern feels categorical: raw sources → compiled wiki has a free/forgetful flavor.

### 4. Mendix / Low-Code
Visual models (microflows, domain models) can be seen as "free" constructions over business requirements, with "forgetful" functors that extract the underlying data or logic.

## How to Explore This in the Wiki

- Create Canvas diagrams showing the unit and counit triangles.
- Use wikilinks as explicit morphisms.
- When ingesting a new source, ask: "What is the free structure being generated here? What is being forgotten?"
- Look for universal properties in agent designs or language features.

## Relations

- [[Functor]] (Adjunctions are built from a pair of functors)
- [[Natural Transformation]] (unit and counit are natural transformations)
- [[Monad]] (Every adjunction gives rise to a monad via G ∘ F)
- [[Monad]] (the other way around: many monads come from adjunctions)

## Formalization

A basic Lean 4 sketch is available here:  
[[formal/category-theory/Adjunction.lean]]

This page is kept at semi-formal level for accessibility. Higher rigor lives in the `formal/` directory.

## Suggested Canvas

Create a diagram with:
- Two boxes (C and D)
- Arrows for F and G
- Unit and counit triangles
- Label them with examples from FP or agent memory

## Sources & Further Reading

- "Category Theory for Programmers" by Bartosz Milewski (excellent for FP audience)
- Mac Lane's *Categories for the Working Mathematician* (classic)
- Papers on free/forgetful constructions in effect systems and memory models

---

*This page is part of the symbiotic LLM Wiki's effort to treat its own structure categorically.*
