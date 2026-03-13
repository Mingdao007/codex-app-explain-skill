---
name: codex-app-explain
description: "Deliver layered teaching and re-explanation for concepts, derivation steps, slide or PDF passages, and bounded homework steps in Codex App when the user asks to explain, re-teach, go from basic to rigorous, or unpack a current blocker. Keep the workflow focused on explanation rather than memory logging, pure file lookup, full assignment completion, or general review."
---

# Codex App Explain

## Scope

Implement a `Codex App` teaching orchestration workflow.

This skill owns teaching orchestration: source binding, prerequisite handling,
depth selection, layered sequencing, route changes after repeated blockage, and
safe stopping at the supported boundary.

Follow the host environment's active formatting rules if they are available.
Otherwise, use this skill's bundled teaching contract and references.

This public skill owns explanation routing, not persistent formatting memory.
When a host environment provides a separate output-rule or rendering workflow,
follow that workflow for notation, labels, and layout while keeping this skill
responsible for teaching route selection.

Keep persistent memory or profile updates in the host environment rather than
inside this skill.

## Trigger Boundary

Use this skill when the user asks for explanation work such as:

- explain a concept
- re-teach a current blocker
- unpack one derivation step
- go from basic to rigorous
- explain one slide or PDF passage
- explain one bounded homework step

Use another workflow when the user is primarily asking to:

- update a persistent preference or memory
- find a file or source without requesting explanation
- write or complete a full assignment
- review code or documents

If the request is mixed, locate the source first and then run this explanation
workflow on the exact object to be explained.

## Read Order

Read only the minimum context needed for the current blocker.

1. The host environment's active answer-format or notation rules, if available
2. The user's cited source material or local project material
3. This skill's bundled references when they help disambiguate the workflow

Use `references/explanation-modes.md` when you need the public mode split for:

- single-concept explanation
- compact prerequisite-chain rebuild
- sentence-by-sentence paper reading
- full layered teaching

For topic material:

- Locate the cited source using available local or project retrieval before
  explaining.
- Load the smallest exact fragment that supports a rigorous explanation.
- Prefer one page, one equation, one excerpt, or one bounded problem part when
  that is enough.

## Core Workflow

### 1. Bind the Object and Scope

Before explaining, explicitly bind:

- what is being explained
- which source fragment it comes from
- which scope applies to it

Name the object first. Then name the source. Then state the scope boundary.

If a missing prerequisite blocks the explanation, insert the minimum
prerequisite object first and say why it is being introduced.

### 2. Load Minimal Evidence

Load only the exact material needed for the current blocker.

Prefer:

- the page, excerpt, or equation under discussion
- the smallest notation source that resolves the ambiguity
- one bounded source fragment rather than a whole document

### 3. Choose Explanation Depth

Choose depth from the user's current request.

Default behavior:

- Give the full layered explanation when the topic is new or the user asks for
  a step-by-step rebuild.
- Answer only the exact blocker when the follow-up targets one local gap.
- Re-answer the same topic directly when the previous version failed on
  clarity, structure, or formatting.

Public mode split:

- `short-concept mode`
  - Use for one concept, one term, one symbol family, or one local blocker.
  - Keep the answer local: definition first, one minimal example when needed,
    then intuition or application only if it still helps.
- `prerequisite-chain mode`
  - Use when the user's real blocker is not one sentence or one formula, but a
    short hidden dependency chain such as state -> trajectory -> flow map ->
    observable.
  - Name the hidden chain, rebuild it in dependency order, then stitch back to
    the source.
- `paper-sentence mode`
  - Use only when the user explicitly asks for sentence-by-sentence or
    passage-by-passage reading of a paper, PDF, or note.
  - Preserve the source sentence visibly, then explain it in a low-barrier
    pass and a deeper interpretation pass.
  - When the quoted source contains OCR noise or poor ASCII-style symbol
    rendering, apply minimal Unicode-friendly cleanup to improve readability.
  - Keep that cleanup display-only: preserve the original English wording and
    meaning, and do not paraphrase, translate, or insert explanation inside
    the quote.
  - Add a local concept note only when that sentence contains a true blocker.
  - Optional paragraph-level and section-level synthesis may follow after the
    relevant local blocks.
- `full-layered mode`
  - Use for full derivations, from-basic-to-rigorous rebuilds, or when the
    topic is new enough that a compact answer would hide the real bridge steps.

### 4. Deliver the Explanation

Deliver the explanation in a deterministic layered order when full depth is
needed:

1. strict definition, assumptions, and symbol roles
2. derivation, bridge steps, or one minimal worked example
3. intuition, interpretation, or application if it helps

Required behavior while explaining:

- Treat each layer as prerequisite support for the next layer.
- Bind each symbol, object, or condition before relying on it.
- State applicability conditions with the formula or relation they govern.
- Fill missing bridge steps when the source jumps.
- Keep the explanation compact unless the user asks for more depth.
- Reply in the user's current conversation language unless the user asks
  otherwise.
- Choose an analogy grounded in the user's background or everyday experience
  when an analogy materially improves understanding.
- In sentence-by-sentence paper reading, keep the source text visually
  separate, preserve its wording, and let the host environment decide the exact
  labels and layout.
- In sentence-by-sentence paper reading, quoted source text may receive
  minimal Unicode-friendly cleanup for OCR noise or poor ASCII-style symbol
  rendering, but that cleanup must remain display-only and must not alter the
  source meaning.
- In sentence-by-sentence paper reading, prefer one low-barrier pass followed
  by one deeper interpretation pass, rather than jumping straight to dense
  formal commentary.
- When a paragraph or section needs a synthesis block, keep that synthesis at
  the paragraph or section level instead of repeating the sentence-by-sentence
  content.

### 5. Change Route After Repeated Blockage

If the user is still blocked after two rounds on the same concept, change the
explanation route rather than repeating the same structure.

Valid route changes include:

- analogy
- counterexample
- concrete-to-abstract rebuild
- fresh minimal numeric example
- coordinate or frame reinterpretation
- object-binding reset

Name the new route before using it so the user can see what changed.

### 6. Stop at the Supported Boundary

If a source is missing, state exactly what is missing and make the smallest
safe assumption.

If multiple sources conflict, state the priority source before explaining.

If the request cannot be supported rigorously from the available material, say
so directly and stop at the supported boundary.

## Output Contract

- Keep the skill focused on teaching orchestration.
- Use absolute file paths only when a local path must be given to the user.
- Use the page number printed on the page itself when a cited page already has
  an internal page number.
- Keep this skill generic and reusable across users and projects.
