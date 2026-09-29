# COLOR-002: Muted Table Text and Opacity

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Content:** Regular text  
**Primary owner:** IG Publisher  
**Status:** Verified for the supplied representative profile pages

## Problem

The Publisher emits inherited text and links with inline `opacity: 0.5`. Opacity
must be calculated after compositing the foreground against each row color.
For inherited `#333333` text, the original treatment fails AA. For links, the
original `#428BCA` fails AA even at full opacity, so an opacity-only correction
cannot repair the link treatment.

## Source transition

Representative generated HTML demonstrates this Publisher-output transition:

```diff
-style="opacity: 0.5"
+style="opacity: 0.87"
```

The link correction also depends on the `project.css` transition from
`#428BCA` to `#0000AA` documented in COLOR-001.

## Non-link inherited text

| Treatment | Base foreground | Opacity | Background | Effective foreground | Ratio | AA | AAA |
|---|---:|---:|---:|---:|---:|---|---|
| Original | <span class="color-swatch" style="--swatch: #333333" aria-hidden="true"></span>`#333333` | 0.50 | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | <span class="color-swatch" style="--swatch: #999999" aria-hidden="true"></span>`#999999` | 2.85:1 | Fail | Fail |
| Original | <span class="color-swatch" style="--swatch: #333333" aria-hidden="true"></span>`#333333` | 0.50 | Stripe <span class="color-swatch" style="--swatch: #F7F7F7" aria-hidden="true"></span>`#F7F7F7` | <span class="color-swatch" style="--swatch: #959595" aria-hidden="true"></span>`#959595` | 2.80:1 | Fail | Fail |
| Practical AA candidate | <span class="color-swatch" style="--swatch: #333333" aria-hidden="true"></span>`#333333` | 0.69 | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | <span class="color-swatch" style="--swatch: #727272" aria-hidden="true"></span>`#727272` | 4.81:1 | Pass | Fail |
| Practical AA candidate | <span class="color-swatch" style="--swatch: #333333" aria-hidden="true"></span>`#333333` | 0.69 | Stripe <span class="color-swatch" style="--swatch: #F7F7F7" aria-hidden="true"></span>`#F7F7F7` | <span class="color-swatch" style="--swatch: #707070" aria-hidden="true"></span>`#707070` | 4.62:1 | Pass | Fail |
| Implemented | <span class="color-swatch" style="--swatch: #333333" aria-hidden="true"></span>`#333333` | 0.87 | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | <span class="color-swatch" style="--swatch: #4E4E4E" aria-hidden="true"></span>`#4E4E4E` | 8.32:1 | Pass | Pass |
| Implemented | <span class="color-swatch" style="--swatch: #333333" aria-hidden="true"></span>`#333333` | 0.87 | Stripe <span class="color-swatch" style="--swatch: #F7F7F7" aria-hidden="true"></span>`#F7F7F7` | <span class="color-swatch" style="--swatch: #4C4C4C" aria-hidden="true"></span>`#4C4C4C` | 8.02:1 | Pass | Pass |

The mathematical transition begins passing at approximately 0.682 for the
supplied colors after 8-bit compositing. `0.69` is reported as the practical AA
candidate to avoid depending on a rounding boundary.

## Muted links

| Treatment | Base foreground | Opacity | Worst supplied ratio | Result |
|---|---:|---:|---:|---|
| Original | <span class="color-swatch" style="--swatch: #428BCA" aria-hidden="true"></span>`#428BCA` | 0.50 | 1.76:1 | Fails AA |
| Original color at full opacity | <span class="color-swatch" style="--swatch: #428BCA" aria-hidden="true"></span>`#428BCA` | 1.00 | 3.39:1 | Still fails AA |
| Example AA treatment | <span class="color-swatch" style="--swatch: #0000AA" aria-hidden="true"></span>`#0000AA` | 0.60 | 4.71:1 | Passes AA |
| Implemented | <span class="color-swatch" style="--swatch: #0000AA" aria-hidden="true"></span>`#0000AA` | 0.87 | 10.17:1 | Passes AAA |

## Acceptance criteria

1. The worst normal foreground/background combination meets the selected target.
2. Parent opacity and transparent ancestors are included in the calculation.
3. Links are tested using their computed link color, not the body text color.
4. Publisher output is corrected upstream rather than only after generation.
