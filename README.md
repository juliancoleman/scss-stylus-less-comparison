# An in-depth comparison of SCSS, Stylus, and LESS

An overview of each pre-processor and their features. These are features native to the parser script and does _not_ include features that can be implemented via the respective API. For example, if LESS has a feature that is impossible for Stylus to obtain without the help of the JS plugin API, it’s listed as _not supporting this feature_.
There are also plenty of other pre-processors that I could compare, but their “market share” is just too minimal for my desire. I’ve also avoided comparing CSS-in-JS pre-processors, such as PostCSS.

## Overview

| Feature             | SCSS            | Stylus     | LESS       |
| ------------------- | --------------- | ---------- | ---------- |
| Language            | Dart/TypeScript | JavaScript | JavaScript |
| File extension      | `.scss`         | `.styl`    | `.less`    |
| Released            | 2006            | 2010       | 2013       |
| Stars               | 13.5K           | 10.8K      | 16.7K      |
| Forks               | 2K              | 1.1K       | 3.5K       |
| Contributors        | 14              | 186        | 241        |
| Used by             | ~               | 1.3M       | ~          |
| Open issues         | ~100            | ~220       | ~152       |
| Commits             | ~400            | ~4K        | ~3K        |
| Default branch name | `main`          | `dev`      | `master`   |
| BLM banner          | ✅              | ❌         | ❌         |

## Syntax

| Feature                                                                                              | SCSS            | Stylus                                                     | LESS                    |
| ---------------------------------------------------------------------------------------------------- | --------------- | ---------------------------------------------------------- | ----------------------- |
| Supports CSS-style syntax                                                                            | ✅              | ✅ ([caveat](https://stylus-lang.com/docs/css-style.html)) | ✅                      |
| Style influences                                                                                     | CSS, JavaScript | CSS, JavaScript, Python, Ruby, Golang                      | CSS                     |
| [Indentation-based](https://stylus-lang.com/docs/selectors.html%23indentation)                       | SASS only       | ✅                                                         | ❌                      |
| Parse errors                                                                                         | ✅              | ✅                                                         | ✅                      |
| Single-line comments                                                                                 | ✅              | ✅                                                         | ✅                      |
| Multi-line comments                                                                                  | ✅              | ✅                                                         | ✅                      |
| [Multi-line buffered comments](https://stylus-lang.com/docs/comments.html#multi-line-buffered)       | ✅              | ✅                                                         | ❌                      |
| [Documentation comments](https://sass-lang.com/documentation/syntax/comments#documentation-comments) | ✅              | ✅                                                         | ❌ [needs verification] |
| Sourcemaps                                                                                           | ✅              | ✅                                                         | ✅                      |

## Style Rules

| Feature                                                                                                  | SCSS                                                                        | Stylus | LESS |
| -------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | ------ | ---- |
| Parent reference                                                                                         | ✅                                                                          | ✅     | ✅   |
| [Partial reference](https://stylus-lang.com/docs/selectors.html#partial-reference)                       | ❌                                                                          | ✅     | ❌   |
| [Ranges in partial references](https://stylus-lang.com/docs/selectors.html#ranges-in-partial-references) | ❌                                                                          | ✅     | ❌   |
| [Initial reference](https://stylus-lang.com/docs/selectors.html#initial-reference)                       | ✅ (using [@at-root](https://sass-lang.com/documentation/at-rules/at-root)) | ✅     | ❌   |
| Relative reference                                                                                       | ❌                                                                          | ✅     | ❌   |
| Root reference                                                                                           | ✅                                                                          | ✅     | ❌   |
| [Property nesting](https://sass-lang.com/documentation/style-rules/declarations#nesting)                 | ✅                                                                          | ❌     | ❌   |
| [Property lookup](https://stylus-lang.com/docs/variables.html#property-lookup)                           | ❌                                                                          | ✅     | ✅   |
| [Placeholder selectors](https://sass-lang.com/documentation/style-rules/placeholder-selectors)           | ✅                                                                          | ❌     | ❌   |

## Variables

| Feature                                                                            | SCSS            | Stylus    | LESS                                                                              |
| ---------------------------------------------------------------------------------- | --------------- | --------- | --------------------------------------------------------------------------------- |
| Assignment operator                                                                | `:`             | `=`       | `:`                                                                               |
| Prefix                                                                             | `$`             |           | `@`                                                                               |
| [Lazy evaluation](https://lesscss.org/features/#variables-feature-lazy-evaluation) | ❌              | ❌        | ✅                                                                                |
| Default values                                                                     | ✅ (`!default`) | ✅ (`?=`) | ✅ ([caveat](https://lesscss.org/features/#variables-feature-default-variables))  |
| Variable reassignment                                                              | ✅              | ✅        | ✅ ([caveat](https://lesscss.org/features/#variables-feature-lazy-evaluation))    |
| Assign variables to variables                                                      | ✅              | ✅        | ✅ ([caveat](https://lesscss.org/features/#variables-feature-variable-variables)) |
| Scoping                                                                            | ✅              | ✅        | ✅ ([caveat](https://lesscss.org/features/#variables-feature-lazy-evaluation))    |
| [Shadowing](https://sass-lang.com/documentation/variables#shadowing)               | ✅              | ✅        | ✅                                                                                |
| [Inline assignment](https://stylus-lang.com/docs/variables.html#property-lookup)   | ❌              | ✅        | ❌                                                                                |
| Properties as variables                                                            | ❌              | ✅        | ✅                                                                                |
| Interpolation                                                                      | ✅              | ✅        | ✅                                                                                |

## Mixins

| Feature                                                                             | SCSS            | Stylus   | LESS            |
| ----------------------------------------------------------------------------------- | --------------- | -------- | --------------- |
| Declaration                                                                         | `@mixin`        |          | `.`             |
| Arguments                                                                           | ✅              | ✅       | ✅              |
| Default values                                                                      | ✅              | ✅       | ✅              |
| Keyword arguments                                                                   | ✅              | ✅       | ✅              |
| Rest params                                                                         | ✅              | ✅       | ✅              |
| Namespaces                                                                          | ❌              | ❌       | ✅              |
| Mixin guards                                                                        | ❌              | ❌       | ✅              |
| [Pattern matching](https://lesscss.org/features/#mixins-feature-pattern-matching)   | ❌              | ❌       | ✅              |
| Mixins as functions                                                                 | ❌              | ✅       | ✅              |
| Property/value accessors                                                            | ❌              | ❌       | ✅              |
| Recursive mixins                                                                    | ❌              | ❌       | ✅              |
| [Content blocks](https://sass-lang.com/documentation/at-rules/mixin#content-blocks) | ✅ (`@content`) | ✅ (`+`) | ✅ (`@rules()`) |
| Mixins as variables                                                                 | ❌              | ✅       | ✅              |
| Parent selector support                                                             | ✅              | ✅       | ✅              |
| Use mixins in mixins                                                                | ✅              | ✅       | ✅              |

## User-Defined Functions

| Feature                                                                                | SCSS        | Stylus           | LESS                                                                                    |
| -------------------------------------------------------------------------------------- | ----------- | ---------------- | --------------------------------------------------------------------------------------- |
| Declaration                                                                            | `@function` |                  | ✅ ([caveat](https://lesscss.org/features/#mixins-feature-mixins-as-functions-feature)) |
| Default values                                                                         | ✅          | ✅               | ✅                                                                                      |
| Rest params                                                                            | ✅          | ✅               | ✅                                                                                      |
| Keyword arguments                                                                      | ✅          | ✅               | ✅                                                                                      |
| Multiple return values                                                                 | ❌          | ✅               | ✅ (named lookups)                                                                      |
| [Anonymous functions](https://stylus-lang.com/docs/functions.html#anonymous-functions) | ❌          | ✅               | ❌                                                                                      |
| `arguments`                                                                            | ❌          | ✅ (`arguments`) | ✅ (`@arguments`)                                                                       |

## Control Flow and Operators

| Feature                                                                        | SCSS                                                                                             | Stylus                                                        | LESS                                                                                                                                                              |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| if / else if / else                                                            | `@if` / `@else if` / `@else`                                                                     | `if` / `else if` / `else`                                     | `if` / `when` ([pattern matching](https://lesscss.org/features/%23mixins-feature-pattern-matching), [guards](https://lesscss.org/features/%23css-guards-feature)) |
| `unless`                                                                       | ❌                                                                                               | ✅                                                            | ❌                                                                                                                                                                |
| Iteration                                                                      | `@for` / `@each` / `@while`                                                                      | `for...in`                                                    | `each`                                                                                                                                                            |
| Equality                                                                       | `==` / `!=`                                                                                      | `==` / `is` / `is a` / `!=` / `is not` / `is not a` / `isnt`  | `=` / `when` / `when not`                                                                                                                                         |
| Relational                                                                     | `<` / `<=` / `>` / `>=`                                                                          | `<` / `<=` / `>` / `>=`                                       | `<` / `<=` / `>` / `>=`                                                                                                                                           |
| Unary                                                                          | `+` / `-`                                                                                        | `!` / `not` / `-` / `+` / `~`                                 | `-`                                                                                                                                                               |
| Numeric                                                                        | `+` / `-` / `*` / `%` ([caveat](https://sass-lang.com/documentation/operators/numeric#division)) | `**` / `*` / `/` / `%` / `+` / `-`                            | `+` / `-` / `*` / `/`                                                                                                                                             |
| Boolean / Logical                                                              | `true` / `false` / `not` / `and` / `or`                                                          | `true` / `false` / `not` / `!` / `&&` / `and` / `\|\|` / `or` | `true` / `false` / `not`/ `and` / `or`                                                                                                                            |
| Character escape                                                               | ✅                                                                                               | ✅                                                            | ❌                                                                                                                                                                |
| String URI encoding                                                            | ❌                                                                                               | ❌                                                            | ✅                                                                                                                                                                |
| String formattng                                                               | ❌                                                                                               | ✅ (`sprintf`)                                                | ✅ (`%` function)                                                                                                                                                 |
| Ranges                                                                         | ❌                                                                                               | ✅                                                            | ✅                                                                                                                                                                |
| Subscript                                                                      | ✅                                                                                               | ✅                                                            | ✅                                                                                                                                                                |
| Shorthand assignment                                                           | ❌                                                                                               | `=` / `+=` / `-=` / `*=` / `/=` / `%=`                        | ❌                                                                                                                                                                |
| Conditional assignment                                                         | ❌ [needs verification]                                                                          | `:=` / `?=`                                                   | ❌ [needs verification]                                                                                                                                           |
| [Existence](https://stylus-lang.com/docs/operators.html#existence-operator-in) | ❌                                                                                               | `in`                                                          | ❌                                                                                                                                                                |
| Type checking                                                                  | ✅                                                                                               | ✅                                                            | ✅                                                                                                                                                                |
| Undefined checkign                                                             | ✅                                                                                               | ✅                                                            | ✅                                                                                                                                                                |
| Type casting                                                                   | ✅                                                                                               | ✅                                                            | ✅                                                                                                                                                                |

## Types

| Feature                                                       | SCSS                    | Stylus                                                | LESS                    |
| ------------------------------------------------------------- | ----------------------- | ----------------------------------------------------- | ----------------------- |
| Number                                                        | ✅                      | ❌                                                    | ✅                      |
| Unit                                                          | ❌                      | ✅                                                    | ✅                      |
| String                                                        | ✅                      | ✅                                                    | ✅                      |
| Color                                                         | ✅                      | ✅                                                    | ✅                      |
| [Path](https://stylus-lang.com/docs/bifs.html#path-functions) | ❌ [needs verification] | ✅                                                    | ❌ [needs verification] |
| List                                                          | ✅                      | ✅                                                    | ✅                      |
| Map                                                           | ✅                      | ✅ ([Hash](https://stylus-lang.com/docs/hashes.html)) | ✅                      |
| Boolean                                                       | ✅                      | ✅                                                    | ✅                      |
| Null                                                          | ✅                      | ✅                                                    | ✅                      |
| Function                                                      | ✅                      | ✅                                                    | ❌                      |

## API

|           | SCSS                                                    | Stylus                                            | LESS                                          |
| --------- | ------------------------------------------------------- | ------------------------------------------------- | --------------------------------------------- |
| Reference | ✅ ([Docs](https://sass-lang.com/documentation/js-api)) | ✅ ([Docs](https://stylus-lang.com/docs/js.html)) | ❌ ([caveat](https://lesscss.org/usage/#api)) |

## Conclusion

Ultimately, you will need to choose the pre-processor that best fits your needs and workflow and my opinion doesn’t actually matter. If you find that LESS is the perfectly sized feature-set, but is missing that one thing that SCSS provides, consider if that feature is so necessary that it warrants a switch that will cause significant code rewrite, or consider using the pre-processor’s API (they each have one). SCSS has significantly more features than LESS, but not as many as Stylus. This can manifest into feeling more of a balanced set of features—not too many, but not too little. Finally, Stylus provides the most features, most of which you probably won’t use in the day-to-day (such as relative references). My best advice is really to _try them all and find what suits your needs best_. No, really. Make a prototype app for each of the pre-processors and find not just the one you like more, but has the most relevant set of features for what your needs are. The only question you should be asking yourself is, _”is this adding the most value to the experience of my users?”_

### Pre-processor Breakdown

LESS is the youngest of the 3 and has the least amount of features, but is the most active Github project when compared to SCSS and Stylus. What this tells me is that _simplicity is key_, and developers are definitely eating it up. In the past, I’ve found ways to work around issues where SCSS or Stylus might provide a function that would make my life a bit easier, but it’s never been a dealbreaker when using LESS. Chances are if you’re developing a theme for the Atom text editor, or you’re working with Ant Design, you will be using LESS. Of the 3, LESS has the most faithful CSS syntax and is easy to get right into the action. It definitely feels more like an extension to native CSS and its goal is to encourage code re-use and avoid duplication.

SCSS on the other hand has incredibly rich features and has been the go-to for every company I’ve worked for thus far. SCSS is the oldest of the 3 and lends itself to be very mature and robust. The downside I’ve run into having looked at some codebases is that SCSS can sometimes feel like too much of a superpower causing complex functions to become a scourge to code maintainability and readability. For example, `@use` and `@forward` are amazing conceptually, but ultimately mask namespaces, so it’s hard to know which mixin or function is coming from which import. While there are so many niceties with SCSS, there are also a lot of personal gripes and complaints. But this reveals a community that is forward-thinking and has growth on their minds. Their cutting-edge features are innovative even when they can feel slightly unintuitive when first added to the language.

Finally, Stylus… Oh, Stylus. Stylus is actually written by TJ Holowaychuk, one of the founding engineers of ExpressJS and Koa, and about a hundred other projects. It’s unclear why he started this project, but he essentially built it overnight (just him), and then it became a direct competitor to SCSS the next morning. Stylus to me feels like someone took the initiative to fix all the dumb crap that exists in SCSS (at-rules, I’m looking in your general direction), and put a bow on it. It is by far the most feature-rich of the 3 pre-processors, but has the lowest amount of stars on Github. However, this is trumped by the sheer amount of contributors working on the project. If the massive feature-set is what your current project needs, then you can’t go wrong with having a little bit extra that you may not need right away, but when you should need those features down the road you won’t need to worry about switching to another pre-processor. Because of the functional paradigm Stylus adds alongside CSS, it lends itself to the same problem where large Stylus projects can become slightly more difficult to read and maintain. However, since there is no ability to `@use` or `@forward`, it’s clear where variables, mixing, and functions are being imported from.

## Final words

Nothing matters more than the users’ experience.
