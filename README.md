## Abstract

A piece of functional programming folklore due to Piponi provides Löb's theorem from modal provability logic with a computational interpretation as an unusual fixed point. Interpreting modal necessity as an arbitrary `Functor` in Haskell, the "type" of Löb's theorem is inhabited by a fixed point function allowing each part of a structure to refer to the whole.

However, `Functor`'s logical interpretation may be used to prove Löb's theorem only by relying on its implicit functorial strength, an axiom not available in the provability modality. As a result, the well known loeb fixed point "cheats" by using functorial strength to implement its recursion.

Rather than `Functor`, a closer Curry analogue to modal logic's Howard inspiration is a closed (semi-)comonad, of which Haskell's `ComonadApply` typeclass provides analogous structure. Its computational interpretation permits the definition of a novel fixed point function allowing each part of a structure to refer to its own context within the whole. This construction further guarantees maximal sharing and asymptotic efficiency superior to loeb for locally contextual computations upon a large class of structures. With the addition of a distributive law, closed comonads may be composed into spaces of arbitrary dimensionality while preserving the performance guarantees of this new fixed point.

From these elements, we construct a small embedded domain-specific language to elegantly express and evaluate multidimensional "spreadsheet-like" recurrences for a variety of cellular automata.

## Building the Paper

You need a working `LaTeX` installation, as well as the programs `latexmk` (which may have come with your `LaTeX` distribution) and `lhs2TeX` (http://www.andres-loeh.de/lhs2tex).

Once you have these installed:

```
lhs2TeX GQFC.lhs -o GQFC.tex; latexmk -pdf GQFC
```

## Playing Along with the Code

You need a working installation of `GHC` version 7.8 or higher, as well as a relatively recent version of `cabal` (supporting sandboxes).

Once you have these installed, you can drop into a REPL for the paper's code like so:

```
cabal sandbox init
cabal install --only-dependencies
cabal configure
cabal repl
```
