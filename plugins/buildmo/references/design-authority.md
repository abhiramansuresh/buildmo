# Design authority

Read this for every UI, visual, interaction, or user-facing copy task.

## Required reading

Read root `DESIGN.md` completely from the current checkout before planning or
editing UI. It is maintained continuously and must never be replaced by a
bundled summary. Also read:

1. `docs/design-specs/design-guardrails.md`.
2. The owning feature or component specification and every required dependency
   it names.
3. `docs/design-specs/design-system/component-map.md`.
4. Relevant component, interaction, behaviour, foundation, and animation
   specifications.
5. The existing implementation and nearby states.

Authority for behaviour is: guardrails, owning spec, related specs, then code
when the documents are silent. Authority for visual and interaction character
is the owning spec, then current `DESIGN.md`, then Figma as visual reference.
Raise contradictions instead of choosing silently.

## Implementation floor

- Reuse a mapped component before creating a variant or replacement.
- Use the product's named tokens and shared interaction helpers. Do not repeat
  values locally when a token exists.
- Respect the single 1920px product canvas and its existing scaling system. Do
  not introduce responsive breakpoints or another coordinate system.
- Place new layered surfaces in the documented overlay hierarchy before
  implementing them.
- Preserve exact approved copy.
- Include loading, empty, error, one, many, long-content, permission, and
  recovery states that apply.
- Preserve input on failure, provide visible async feedback, and block duplicate
  triggers.
- Check keyboard access, focus, contrast, labels, reading order, target size,
  and reduced motion.
- Never implement `Future Considerations`.

External design skills may help critique or simplify an implementation, but
they never overrule Guru's specifications or `DESIGN.md`. Do not create a
generic `PRODUCT.md` in Guru to satisfy another skill.
