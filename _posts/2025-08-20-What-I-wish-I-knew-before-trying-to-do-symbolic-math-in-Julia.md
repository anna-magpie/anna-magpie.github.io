---
layout: default
title: "What I wish I knew before trying to do symbolic math in Julia"
tags: [Julia, performance, multiple-dispatch]
---
I've been working on a project recently which requires me to programatically convert Boolean DAGs into continuous variable formulations in order to do math on them. This has lead me into a rabbithole of metaprogramming and programmming language theory, this blog post is a documentation of one particular problem I ran into as a result. 

The most popular julia library for symbolic math is symbolics.jl, and in this package the standard method for generating objects which you can perform algebraic manipulations on is the @variables macro. The behaviour of macros, as it turns out, is less than entirely intuitive. Initially I tried 

```
for name in list of nodes
        symbolicslist = []
        push!(symbolicslist, @variables name)
end
```
The output of this was not - as I had been expecting - a list containing the names of my nodes instantiated as symbolic types, but rather a single element list consisting of the element ```name```. And this is how I as a novice programmer unknowingly ran into the distinction between runtime evaluation and compile time evaluation. 

#### What exactly is a lisp style macro?
I spent some time frustratedly reading the docs, and trying to find other ways to convert my values into something usable by Symbolics.jl before I stopped myself to ask the question what @variables was - up until now I had more or less assumed it behaved like a function. This is not the case, @variables is a macro, specifically it is a Lisp style macro, a feature Julia provides extensive support for. A macro is a 
