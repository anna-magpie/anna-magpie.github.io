---
layout: default
title: "Why care about Julia"
tags: [Julia, performance, multiple-dispatch]
---

Julia collapses the two-language problem: you can prototype and ship high-performance code in one language.

- **Multiple dispatch** expresses algorithms over relationships between types.
- **JIT + LLVM** gives C-like performance without hand-written C.
- **Parametric types** (via `where`/`UnionAll`) make generic code efficient.

```julia
f(x::Vector{T}, y::T) where T = ...
