# Teaching Principles

These principles define the public teaching contract for `codex-app-explain`.

## 1. Explain the right object first

- Name the object before unpacking symbols or manipulation steps.
- Bind the source fragment and scope before expanding the explanation.

## 2. Keep evidence minimal

- Load the smallest source fragment that can support a rigorous explanation.
- Prefer one local page, excerpt, equation, or bounded problem part.

## 3. Layer explanations deterministically

- Use this default order when a full explanation is needed:
  1. strict definition, assumptions, and symbol roles
  2. derivation, bridge steps, or one minimal example
  3. intuition, interpretation, or application when helpful

## 4. Bind dependencies before use

- Define each symbol, condition, object, or scope boundary before relying on
  it.
- Insert the minimum prerequisite object when the main explanation would
  otherwise be blocked.

## 5. Keep the explanation compact and rigorous

- Stay concise unless the user asks for more depth.
- Fill missing bridge steps instead of hiding them.
- State applicability conditions with the relation they govern.

## 6. Adapt to the user's language

- Reply in the user's current conversation language unless the user asks
  otherwise.
- Keep terminology consistent across one explanation.
