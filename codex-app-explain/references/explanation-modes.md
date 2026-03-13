# Explanation Modes

This reference summarizes the public mode split used by `codex-app-explain`.

## 1. `short-concept mode`

Use this mode when the user wants one concept, one term, one symbol family, or
one local blocker explained.

Default shape:

1. strict definition
2. one minimal example or bridge step when needed
3. intuition or application only if it still helps

Use this mode to stay local rather than expanding into a longer lecture.

If the blocker is a logic-role confusion such as statement versus proof, begin
with one minimal plain example that stays close to the source sentence pattern,
then give the direct role judgment before returning to the formal object.

If the blocker is an object-boundary confusion, use one local contrast example
or compact counterexample at the first useful distinction point.

## 2. `prerequisite-chain mode`

Use this mode when the visible question points at one local sentence or symbol,
but the real blocker is a short hidden dependency chain.

Typical examples:

- state -> trajectory -> flow map
- observable -> operator -> eigenfunction
- frame -> coordinate choice -> local formula

Default shape:

1. name the hidden chain
2. rebuild the chain in dependency order
3. stitch back to the original local question

## 3. `paper-sentence mode`

Use this mode only when the user explicitly asks to read a paper, PDF, or note
sentence by sentence or passage by passage.

Public behavior:

- preserve the source sentence visibly
- keep the source wording intact while allowing host-approved readability
  cleanup for OCR noise or poor symbol rendering
- when readability cleanup is needed, use minimal Unicode-friendly symbol
  normalization only; do not paraphrase, translate, or add explanation inside
  the quote
- explain each sentence in two passes:
  - one low-barrier pass
  - one deeper interpretation pass
- add a local concept note only when the sentence contains a true blocker
- allow a paragraph-level or section-level synthesis block after the relevant
  local units
- let the host environment own the exact labels, divider placement, and
  sentence-block layout when separate rendering rules already exist

This mode is for reading support, not for replacing the paper with a new
summary.

## 4. `full-layered mode`

Use this mode when the user asks for a full rebuild such as:

- from basic to rigorous
- derive this step
- teach me this method
- unpack the whole workflow

Default layered order:

1. strict definition, assumptions, and symbol roles
2. derivation, bridge steps, or one minimal worked example
3. intuition, interpretation, or application if it helps

When long explanations contain a clear functional shift, for example from a
local example to a formal source or from a direct verdict to a synthesis,
prefer a visible structural separator when the host environment supports one.

## 5. Route ownership

- `codex-app-explain` owns teaching-route selection and stop conditions.
- The host environment owns persistent memory, user-specific formatting, and
  rendering details when those rules exist.
- A separate output-rules skill may own notation and layout. In that case,
  this skill still owns which teaching mode to use.
