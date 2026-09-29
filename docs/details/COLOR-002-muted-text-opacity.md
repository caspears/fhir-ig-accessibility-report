# COLOR-002: Muted Table Text and Opacity

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Content:** Regular text unless a verified large-text exception applies  
**Primary owner:** IG Publisher  
**Status:** Remediation uses `opacity: 0.87`; all contexts require verification

## Problem

Some generated descriptions and cardinalities use reduced opacity. Because
opacity composites the entire element with the background, the effective text
color differs between white and alternating table rows.

## Source transition

```diff
 .generated-muted-text {
-  opacity: 0.5;
+  opacity: 0.87;
 }
```

## Required calculations

| Treatment | Base foreground | Opacity | Background | Effective foreground | Ratio | AA | AAA |
|---|---:|---:|---:|---:|---:|---|---|
| Original | TBD | 0.5 | White row TBD | Calculated | TBD | TBD | TBD |
| Original | TBD | 0.5 | Striped row TBD | Calculated | TBD | TBD | TBD |
| Minimum AA | TBD | Calculated | Worst background | Calculated | At least 4.5:1 | Pass | Not necessarily |
| Implemented | TBD | 0.87 | White row TBD | Calculated | TBD | Pass expected | Verify |
| Implemented | TBD | 0.87 | Striped row TBD | Calculated | TBD | Pass expected | Verify |

## Implementation consideration

Where possible, prefer an explicit accessible text color over applying
`opacity` to the entire element. Element opacity can also affect icons,
decorations, and nested content and is harder to reason about across multiple
backgrounds.

## Acceptance criteria

1. The worst normal foreground/background combination meets the selected target.
2. Parent opacity and transparent ancestors are included in the calculation.
3. Information is not visually suppressed merely because it is secondary.
4. The final treatment is implemented in Publisher CSS rather than added later.

