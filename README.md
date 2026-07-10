# clap.rs — The Complete Tutorial

> A self-contained, offline-friendly reference for learning `clap` in Rust —
> from your first argument to production-grade CLI patterns.

---

## Why this exists

The official `clap` docs are comprehensive, but they assume you already know
what you're looking for. For a learner, jumping between docs.rs, the clap book,
and random Stack Overflow threads is exhausting — and the concepts don't connect.

This tutorial was built to be the **one file you open instead**. Every concept
builds on the previous one. You read it top to bottom once, then use it as a
reference forever.

---

## What's inside

The tutorial is a single `.html` file you open in any browser. No server, no
internet required after download.

```
index.html
```

### Layout

The page is split into two panels:

```
┌─────────────────────┬──────────────────────────────────────────┐
│                     │                                          │
│   Sidebar           │   Main content                          │
│                     │                                          │
│   Navigation        │   Chapter heading                       │
│   with sections     │   Explanation in plain language         │
│   and progress      │                                          │
│   bar               │   ┌──────────────────────────────────┐  │
│                     │   │  // syntax-highlighted code      │  │
│   Scroll to jump    │   │  with copy button                │  │
│   to any chapter    │   └──────────────────────────────────┘  │
│                     │                                          │
│                     │   $ terminal output block               │
│                     │                                          │
│                     │   ╔══════════════════════════════════╗  │
│                     │   ║  tip / warning / info callout    ║  │
│                     │   ╚══════════════════════════════════╝  │
│                     │                                          │
└─────────────────────┴──────────────────────────────────────────┘
```

### Chapters

| # | Chapter | What you learn |
|---|---------|----------------|
| 0 | What is clap? | Mental model: args → Rust struct |
| 1 | Installation | Cargo.toml, feature flags |
| 2 | First Program | `#[derive(Parser)]`, doc comments as help text |
| 3 | Derive vs Builder | Why derive is always the right choice |
| 4 | Args, Options, Flags | The three building blocks, side by side |
| 5 | Options & Flags Deep Dive | Counting flags (`-vvv`), negatable flags |
| 6 | Parsing into Rust Types | `String`, `u16`, `PathBuf`, `IpAddr`, `Option<T>` |
| 7 | Required & Optional | How your field's type controls this |
| 8 | Default Values | `default_value` vs `default_value_t`, computed defaults |
| 9 | Subcommands | Enums as subcommands, nested args per variant |
| 10 | Required Subcommands | `Option<Commands>` for optional subcommands |
| 11 | Global Arguments | Args that work before and after subcommands |
| 12 | Built-in Validation | `.range()` on value parsers |
| 13 | Custom Validators | Write any `fn(&str) -> Result<T, E>` |
| 14 | Conflicts & Requires | Encode mutual exclusion and dependencies |
| 15 | ValueEnum | Restrict to a known set of string values |
| 16 | Environment Variables | `env = "VAR"`, precedence over env |
| 17 | Config Files | The right pattern for CLI + file + env layering |
| 18 | Multiple Values | `Vec<T>`, `num_args`, `value_delimiter` |
| 19 | Argument Groups | "exactly one of these must be given" |
| 20 | Custom Help & Version | `after_help`, `env!("CARGO_PKG_VERSION")`, hiding args |
| 21 | Error Handling | `try_parse()`, `parse_from()`, writing tests |
| — | Cheatsheet | Every `#[arg(...)]` and `#[command(...)]` attribute |
| — | Real-world Patterns | Git-style tool, server, pipe-friendly CLI |

---

## How to use it

**Learning pass** — read chapters 0 through 9 in order. By the end you can
build any CLI that doesn't need fancy validation. That covers 80% of real tools.

**As a reference** — use the sidebar to jump directly to what you need.
The cheatsheet at the bottom has every attribute in one table.

**Offline** — download the file once. It uses a Google Fonts import for
JetBrains Mono; if you're offline, your browser will fall back to your system
monospace font. Everything else is self-contained.

---

## Design decisions

**Single file.** No build step, no npm, no bundler. Open it and it works.

**Terminal aesthetic.** `clap` is a CLI library — the dark theme and green
accents match the environment where you'll actually use it.

**Code you can copy.** Every block has a copy button. The syntax highlighting
maps to standard Rust token categories (keywords, types, strings, macros,
attributes) so your eye learns to read real code faster.

**Callouts signal importance.** Green = tip you'll use often. Yellow = common
mistake. Blue = background context. Red = breaking behaviour to watch out for.

**Doc comments are first-class.** Every code example shows `/// doc comments`
on struct fields — because that's where clap reads your help text from, and
most beginner examples skip this.

---

## The one thing to remember

```
/// This doc comment becomes the help text
#[arg(short, long)]
output: Option<PathBuf>,
```

Everything else is just variations on this pattern.

---

## Prerequisites

- Rust installed via `rustup`
- Comfortable reading a basic struct and enum
- Able to run `cargo new` and `cargo run`

No prior CLI library experience needed.

---

## Versions

This tutorial targets **clap 4.x** with the **derive API**. The builder API
(the older style) is mentioned once in Chapter 3 so you can recognise it in
the wild, then set aside.

---

## Warning

I used AI as a learning assistant to explain concepts I found difficult in the official documentation, then verified examples and behavior against the official clap documentation and by running the code myself.

---

## Help

If you find any mistakes or outdated information, please open an issue or submit a pull request.
---

*Built as a learning companion. Not affiliated with the clap project.*
