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
