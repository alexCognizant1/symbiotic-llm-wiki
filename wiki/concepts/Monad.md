# Monad

**type:** concept  
**formalization_level:** semi-formal  
**formalization_debt:** medium

## Human Insight

Monads are one of the most powerful unifying abstractions across functional programming and increasingly relevant to agent architectures (effect handling, state, non-determinism).

## Agent Synthesis

A monad consists of:
- A type constructor `M`
- `return : A → M A`
- `bind : M A → (A → M B) → M B`

Satisfying the three monad laws.

Common in:
- Haskell, Scala, F#
- Effect systems
- Agent memory and planning loops

## Relations

- [[Adjunction]] (many monads arise from adjunctions)
- [[Natural Transformation]] (monad laws can be expressed via naturality)

## Formalization

See attempts in `[[formal/functional-programming/Monad.lean]]` (sketch).

## Sources

- [[raw/papers/wadler-monads]]
- Various FP language specifications
