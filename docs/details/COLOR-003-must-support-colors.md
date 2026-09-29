# COLOR-003: Must Support Badge

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Primary owner:** IG Publisher  
**Status:** Verified in the supplied representative profile pages

## Source transition

The supplied HL7 page contains white `S` text on `#D50000`. The remediated CDC
page contains white `S` text on `#B60000`:

```diff
-color: white; background-color: #D50000
+color: white; background-color: #B60000
```

## Color preview and results

| Treatment | Badge background | Text | Ratio | AA | AAA |
|---|---|---:|---:|---|---|
| Original | <span class="color-swatch" style="--swatch: #D50000" aria-hidden="true"></span>`#D50000` | White `#FFFFFF` | 5.48:1 | Pass | Fail |
| Implemented | <span class="color-swatch" style="--swatch: #B60000" aria-hidden="true"></span>`#B60000` | White `#FFFFFF` | 7.03:1 | Pass | Pass |

No color change was required for AA: the original badge already exceeded
4.5:1. The darker treatment was required only for the selected AAA regular-text
target. The alternating table row does not affect this calculation because the
glyph is rendered against the badge's opaque background.

## Color-independent meaning

The visible `S`, its tooltip or accessible description, and surrounding table
semantics must continue to convey Must Support status without relying on red
alone.

