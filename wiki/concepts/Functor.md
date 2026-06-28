# Functor

**type:** theory  
**formalization_level:** semi-formal

## Human Insight

Functors are the "structure-preserving maps" between categories. They are how we translate concepts from one domain to another while respecting the relationships (arrows) between them.

In this wiki, wikilinks and cross-references behave like functors when we map ideas across papers, languages, or agent architectures.

## Definition

A functor **F: C → D** between categories assigns:
- To every object X in C an object F(X) in D
- To every morphism f: X → Y in C a morphism F(f): F(X) → F(Y) in D

such that:
- F(id_X) = id_{F(X)}
- F(g ∘ f) = F(g) ∘ F(f)

## Examples in This Project

- Mapping between different programming languages (Haskell Functor → Scala Functor → Rust trait)
- Mapping raw sources to synthesized wiki pages
- Agent perception functors (raw input → structured memory)
- Mendix domain models as functors from business concepts to executable structures

## Relations

- [[Adjunction]] (built from a pair of functors)
- [[Natural Transformation]] (maps between functors)
- [[Monad]] (a functor equipped with extra structure)

See [[Adjunction]] for deeper connections.
