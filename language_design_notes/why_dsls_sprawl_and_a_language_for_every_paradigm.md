# Why DSLs sprawl, and what a "paradigms as libraries" language would need

Two connected questions:

1. What patterns keep producing overly opinionated features and domain-specific languages (DSLs)?
2. What core components would a language need so that every paradigm (assembly, array, logic, functional, Lisp-style, ownership, proof, markup, compiler IR, systems work) could be delivered as a library instead of a new language?

The short version: most bad DSLs come from **freezing a guess into syntax too early**. The language in part 2 is an attempt to make that guess cheap to undo, by giving libraries the powers that are normally reserved for language designers.

---

## Contents

- [Part 1: Why opinionated tools and DSLs keep appearing](#part-1-why-opinionated-tools-and-dsls-keep-appearing)
  - [How they get started](#how-they-get-started)
  - [Why they stick](#why-they-stick)
  - [Structural causes](#structural-causes)
  - [Named laws and patterns](#named-laws-and-patterns)
  - [Habits that help](#habits-that-help)
- [Part 2: A language where paradigms are libraries](#part-2-a-language-where-paradigms-are-libraries)
  - [Design principle](#design-principle)
  - [The seven pillars](#the-seven-pillars)
  - [How each target paradigm maps onto the pillars](#how-each-target-paradigm-maps-onto-the-pillars)
  - [Where it gets hard](#where-it-gets-hard)
  - [Who already has which piece](#who-already-has-which-piece)
- [Further reading](#further-reading)

---

## Part 1: Why opinionated tools and DSLs keep appearing

Most of them come from treating one team's situation as if it were the general case, and from building abstractions before anyone has seen the variation they are meant to cover.

### How they get started

| Pattern | What happens | Example |
| --- | --- | --- |
| **Generalizing from one example** | The first use case becomes the model, so its quirks turn into core concepts. | A deploy tool whose core object is "a Rails app on one server." |
| **Encoding the workflow, not the primitives** | The tool hardcodes *how* one team works (sequence, naming, approval steps) instead of the operations underneath. Fine until a second team arrives. | Ticket systems with a fixed, unskippable state machine. |
| **Configuration that grew up** | A config file gains conditionals, then variables, then loops. Now there is an accidental language with no debugger, no types and no tooling. | Ant's XML build files, YAML-based CI pipelines with `if:` expressions and matrix expansion, templating engines, Access macros. |
| **Avoiding the host language** | "Non-programmers will write this" justifies a DSL. Then programmers end up writing it anyway, in a worse language. | Rule engines and "low-code" workflow languages maintained by the engineering team. |

The "configuration that grew up" path is common enough to have a name: Mike Hadlow's **configuration complexity clock** describes the cycle of hardcoded values → config file → rules engine → DSL → "this DSL is too limited, let's just write code" → back to the start.

### Why they stick

- **Novelty is fun, and the cost lands later.** Designing a language feels like leverage. The bill for docs, error messages, editor support and onboarding arrives later, often for someone else.
- **Not invented here, plus missing knowledge of prior art.** People don't know that Datalog, Lua, Lisp macros, or a plain library with a fluent API already solves the problem.
- **The opinion is the product.** An opinionated framework sells on "convention over configuration." That works inside its sweet spot, and its authors rarely meet the users outside it.
- **Escape hatches get added last, or never.** Without a clean way down to the general-purpose layer, every edge case becomes a feature request. Each one gets bolted on, and the opinions harden.
- **Sunk cost and lock-in.** Once data or scripts exist in the DSL, extending it is cheaper than migrating away.

### Structural causes

- **Conway's law.** A system's boundaries mirror the communication structure of the organization that built it, so a tool's "opinions" are often one team's ownership boundaries.
- **The designer isn't the maintainer.** Promotion and visibility reward building new things, not keeping them alive.
- **Domain experts and implementers are different people.** The implementer guesses the domain's shape and freezes that guess into syntax.

### Named laws and patterns

These are useful shorthand when arguing against a new DSL in a design review:

- **Greenspun's tenth rule:** "Any sufficiently complicated C or Fortran program contains an ad hoc, informally-specified, bug-ridden, slow implementation of half of Common Lisp." The modern version is the YAML file that slowly becomes a programming language.
- **Inner-platform effect:** a system so configurable that it becomes a poor replica of the platform it was built on (for example, a database schema that stores tables as rows).
- **Rule of three:** wait for three real instances before abstracting. Two is a coincidence, three is a pattern.
- **Wadler's law:** in language design, the time spent discussing a feature grows with how superficial it is (syntax gets far more debate than semantics). A reminder that new syntax is the cheap, visible part.
- **Guy Steele, "Growing a Language" (1998):** a language should be designed so that users can grow it, because no designer can predict everything users will need. This is the thesis Part 2 builds on.

### Habits that help

1. **Start as a library in the host language.** Promote it to a DSL only when the library's ergonomics have clearly failed.
2. **Make the opinionated layer sugar over an unopinionated core**, and expose that core too.
3. **Wait for three real use cases** before abstracting.
4. **Choose data over code.** Prefer declarative formats that existing tools can read (JSON, TOML, SQL tables) before inventing syntax.
5. **Plan the escape hatch on day one.** Every DSL construct should have a documented way to drop to the host language.
6. **Budget for tooling up front.** If there is no plan for error messages, highlighting and a debugger, there is no plan for a language.

> The underlying problem is that it's cheap to put a guess into syntax and expensive to take it back out. With a library, you can deprecate a function. With a language, you're stuck keeping its grammar working.

---

## Part 2: A language where paradigms are libraries

**Question:** what core components would a language need to provide all the programming paradigms, and more, as libraries? Targets: Assembly, APL, Prolog, Haskell, Lisp, Rust, Lean, HTML/XML/Markdown/LaTeX, LLVM, MLIR, networking, drivers and firmware.

### Design principle

The core has to **stay out of the decisions the paradigms disagree on**:

- evaluation order (strict vs. lazy),
- memory management (GC vs. ownership vs. manual),
- how strict the types are (untyped vs. dependent),
- syntax.

And it has to be **very strong at metaprogramming**, so libraries can make those decisions themselves. This is the "languages as libraries" idea that Racket's authors named and demonstrated.

### The seven pillars

#### 1. Extensible syntax with scoping

- A parser that libraries can extend, so APL glyphs, Prolog clauses, HTML and LaTeX blocks can be written as they normally are.
- Hygienic macros, plus dialects that apply only inside a given region of code (a module, a block, a quoted literal) so they don't collide.
- **Prior art:** Racket's `#lang` line, which picks the reader and semantics per module; Lean 4's user-extensible parser and elaborator ("Beyond Notations"); Rust's procedural macros for the narrower token-stream version.

#### 2. Staging: the compiler as a library

- Full compile-time execution with access to the compiler's internals: syntax trees, types and IR.
- A library can then *be* a compiler pass. That is how you get APL-style loop fusion, Prolog's clause indexing, or a parser generator, all without changing the compiler.
- **Prior art:** Terra (Lua that stages low-level code), Zig's `comptime`, MetaOCaml's typed quotes and splices, Scala's Lightweight Modular Staging.

#### 3. A multi-level, extensible IR

- MLIR-style *dialects*, so a library can define its own IR level and how it lowers. For example: array ops → affine loops → LLVM IR → machine code.
- Exposing this is also what makes "LLVM/MLIR as a library" possible, instead of LLVM being a hidden backend.
- Each lowering step stays inspectable and testable on its own, which also helps the error-message story in pillar 7.

#### 4. A type theory that can grade usage

- Dependent types for Lean-style proofs, plus linear or affine tracking for Rust-style ownership.
- **Quantitative type theory** (used by Idris 2) handles both in one system: every variable carries a usage count of 0, 1, or many. Count 0 means "compile-time only", so proofs are erased at runtime and cost nothing. Count 1 gives linear resources.
- A small trusted kernel, with tactics written as ordinary metaprograms (pillar 2), as in Lean 4.
- Gradual typing at the edges, so untyped scripting and Lisp-style exploration remain possible.

#### 5. Algebraic effects and delimited continuations

- One mechanism that covers exceptions, generators, async/await, mutable state and backtracking nondeterminism. Backtracking is most of Prolog's search strategy.
- Add logic variables and unification as a library, and Prolog is mostly done. (miniKanren shows how small this core can be.)
- Laziness becomes a library (thunks and memoization), so the core can evaluate strictly and still host Haskell-style code.
- **Prior art:** Koka and Effekt (effect-typed languages), OCaml 5's effect handlers, Eff.

#### 6. Bare-metal control with no required runtime

- Optional GC: raw pointers, explicit memory layout, `volatile`, atomics and a clearly specified memory model.
- Inline assembly, interrupt calling conventions, linker-script control and a freestanding mode for firmware.
- C ABI interop for drivers and existing ecosystems.
- **Prior art:** Rust's `no_std`, Zig's freestanding targets, C.

#### 7. Hooks for tooling and error messages

- The step most often skipped. A library-defined dialect must be able to supply its own diagnostics, syntax highlighting, formatting and language-server behavior.
- Without this you get the problem from Part 1: DSLs with terrible errors.
- **Prior art:** Lean 4's info trees and widgets, Racket's DrRacket integration, Elm's and Rust's emphasis on error-message quality.

### How each target paradigm maps onto the pillars

| Target | What the library provides | Pillars it leans on |
| --- | --- | --- |
| **Assembly** | Inline asm blocks, register and calling-convention types | 1, 6 |
| **APL** | Glyph syntax, rank-polymorphic arrays, fusion pass that lowers to loops | 1, 2, 3 |
| **Prolog** | Clause syntax, unification, backtracking search, clause indexing | 1, 2, 5 |
| **Haskell** | Lazy thunks, type classes, pure-by-default effect discipline | 4, 5 |
| **Lisp** | S-expression reader, `quote`/`eval`, REPL with gradual typing | 1, 2, 4 |
| **Rust** | Ownership and borrowing via linear/affine usage counts, `no_std` mode | 4, 6 |
| **Lean** | Dependent types, proof kernel, tactic metaprograms | 2, 4, 7 |
| **HTML / XML / Markdown / LaTeX** | Embedded document syntaxes that build typed trees, checked at compile time | 1, 2 |
| **LLVM / MLIR** | IR construction and lowering as first-class library APIs | 3 |
| **Networking** | Async I/O and protocols as effect handlers; parsers generated at compile time | 2, 5 |
| **Drivers / firmware** | MMIO with `volatile`, interrupt handlers, linker control, no runtime | 6 |

### Where it gets hard

- **Phase separation.** With dependent types and staging both in play, compile time and runtime blur together. The language needs a clear model of what runs when (Racket's phase levels are one answer).
- **Effects vs. ownership.** Continuations that can resume more than once (needed for backtracking) conflict with linear resources, which must be used exactly once. OCaml 5 sidesteps this by allowing only one-shot continuations, which rules out the Prolog use case. The type system has to track which handlers are multi-shot.
- **Compile times.** A compiler that runs libraries as passes can get slow, and staged code is hard to cache incrementally.
- **Fragmentation.** If every library brings its own syntax, the ecosystem splits into mutually unreadable dialects, much as happened with Lisp macros. Conventions (and pillar 7 tooling) matter as much as the mechanism.
- **Trust.** Libraries that act as compiler passes can miscompile code. A small verified kernel (pillar 4) helps for proofs, but not for performance passes.

### Who already has which piece

| Language / system | Pillars it covers well |
| --- | --- |
| **Racket** | 1 (syntax, `#lang`), 2 (macros, phases), 7 (DrRacket) |
| **Lean 4** | 1, 2, 4 (dependent types, tactics), 7 |
| **Zig** | 2 (`comptime`), 6 (freestanding, no hidden runtime) |
| **Idris 2** | 4 (quantitative type theory) |
| **Koka / Effekt** | 5 (typed algebraic effects) |
| **MLIR** | 3 (dialects and progressive lowering) |
| **Rust** | 6, partial 4 (ownership, but not dependent types) |
| **Terra** | 2, 6 (staged low-level code) |

No existing language covers all of this. A credible design would mostly be about getting **pillars 2, 4 and 5 to coexist**: staging, a usage-graded dependent type theory, and multi-shot effects that respect linear resources.

---

## Further reading

- Guy L. Steele Jr., *Growing a Language*, OOPSLA 1998 keynote. A language should be designed to be grown by its users.
- Sam Tobin-Hochstadt et al., *Languages as Libraries*, PLDI 2011. Racket's approach to building languages as libraries.
- Sebastian Ullrich and Leonardo de Moura, *Beyond Notations: Hygienic Macro Expansion for Theorem Proving Languages*, IJCAR 2020. Lean 4's extensible syntax.
- Chris Lattner et al., *MLIR: Scaling Compiler Infrastructure for Domain Specific Computation*, CGO 2021.
- Edwin Brady, *Idris 2: Quantitative Type Theory in Practice*, ECOOP 2021.
- Robert Atkey, *Syntax and Semantics of Quantitative Type Theory*, LICS 2018.
- Daan Leijen, *Koka: Programming with Row-Polymorphic Effect Types*, MSFP 2014.
- Zachary DeVito et al., *Terra: A Multi-Stage Language for High-Performance Computing*, PLDI 2013.
- Tiark Rompf and Martin Odersky, *Lightweight Modular Staging*, GPCE 2010.
- Daniel P. Friedman, William E. Byrd, Oleg Kiselyov, *The Reasoned Schemer* (miniKanren).
- Mike Hadlow, *The Configuration Complexity Clock* (blog post, 2012).
- Melvin Conway, *How Do Committees Invent?*, Datamation 1968 (the origin of Conway's law).
