# Color and Contrast Evaluation Method

[Back to Start Here](index.md) · [Quick Reference](01-quick-reference.md)

## Applicable thresholds

- WCAG 2.1 SC 1.4.3 requires at least 4.5:1 for regular text and 3:1
  for large text at Level AA.
- WCAG 2.1 SC 1.4.6 requires at least 7:1 for regular text and 4.5:1
  for large text at Level AAA.
- WCAG 2.1 SC 1.4.11 generally requires 3:1 for meaningful graphical
  objects and visual information needed to identify user-interface components.

References:

- [WCAG 2.1 — Contrast Minimum](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html)
- [WCAG 2.1 — Contrast Enhanced](https://www.w3.org/WAI/WCAG21/Understanding/contrast-enhanced.html)
- [WCAG 2.1 — Non-text Contrast](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html)

## Evaluation unit

The evaluation unit is a rendered foreground/background combination, not an
isolated CSS color. One CSS selector can therefore produce several report rows.

For each affected selector, evaluate:

1. Computed foreground color
2. Effective background through transparent ancestors
3. Element and ancestor opacity
4. Font size and weight
5. White, striped, header, badge, and other normal backgrounds
6. Hover, focus, active, and visited states where applicable
7. The lowest contrast ratio across the normal contexts

## AA versus the implemented AAA treatment

The report records three states:

| State | Meaning |
|---|---|
| Original | Presentation before remediation |
| Minimum AA candidate | Closest practical treatment that exceeds the applicable AA threshold in every identified context |
| Implemented treatment | The actual remediation, normally targeting AAA for regular text |

WCAG specifies a ratio, not a unique replacement color. A “minimum AA
candidate” therefore means the closest practical value that preserves the
design intent and passes every identified background without relying on
rounding.

## Opacity

Opacity is evaluated after compositing the foreground over the effective
background. The same declared text color and opacity can produce different
effective colors on white and striped rows. Screenshot pixels are useful for
finding contexts but are not the authoritative source for calculation; computed
CSS values are used.

