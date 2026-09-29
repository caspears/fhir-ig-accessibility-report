# COLOR-001: Profile-Table Links

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Content:** Regular text  
**Primary owner:** IG Publisher CSS  
**Status:** Sample—source analysis required

## Problem

Blue links appear on more than one effective background in generated profile
tables, including white and alternating light-gray rows. The same link color
must be evaluated separately against each background and in each styled
interaction state.

## Source transition

```diff
 .profile-table a {
-  color: ORIGINAL_LINK_COLOR;
+  color: IMPLEMENTED_LINK_COLOR;
 }
```

## Contrast results

| Treatment | State | Foreground | Background | Ratio | AA | AAA |
|---|---|---:|---:|---:|---|---|
| Original | Normal, white row | TBD | TBD | TBD | TBD | TBD |
| Original | Normal, striped row | TBD | TBD | TBD | TBD | TBD |
| Original | Hover/focus, white row | TBD | TBD | TBD | TBD | TBD |
| Original | Hover/focus, striped row | TBD | TBD | TBD | TBD | TBD |
| Minimum AA | Worst identified context | TBD | TBD | TBD | Pass | Not necessarily |
| Implemented | Worst identified context | TBD | TBD | TBD | Pass | Target: Pass |

## Decision

Select one link color only if it passes against every normal table background.
If that is inconsistent with the intended design, use context-specific rules.
Do not use color alone to distinguish links where the surrounding text would
otherwise make them indistinguishable.

## Acceptance criteria

1. Normal link text meets the selected contrast target on white and striped rows.
2. Hover, focus, active, and visited states meet the applicable target.
3. Links remain identifiable without relying solely on color where required.
4. Newly generated pages do not need color postprocessing.

