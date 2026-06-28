# Natural Transformation

**type:** theory  
**formalization_level:** intuition

## Human Insight

If functors are "mappings between categories," natural transformations are "mappings between functors" that respect the structure in a coherent way.

They are the "arrows between arrows."

## Definition (Intuitive)

Given two functors F, G : C → D, a natural transformation η : F ⇒ G assigns to every object X a morphism η_X : F(X) → G(X) such that for any f : X → Y the following diagram commutes:

F(X) --F(f)--> F(Y)
 |               |
η_X            η_Y
 |               |
 v               v
G(X) --G(f)--> G(Y)

## Relevance to the Wiki

- The "unit" and "counit" of an adjunction are natural transformations.
- When the LLM updates multiple related pages consistently after ingesting a new source, it is (informally) applying something like a natural transformation.
- Consistent patterns across different agent memory implementations can be expressed as natural transformations.

## Relations

- [[Functor]]
- [[Adjunction]]
- [[Monad]]

For formal treatment, see the formal/ directory and the Adjunction page.
