# COLOR-004: Generated Syntax Colors

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Primary owner:** IG Publisher  
**Status:** Open AA gap identified during source review

## Finding

The supplied representative profile pages include Publisher-generated JSON-like
syntax views containing visible comment markers with inline `color: Gray`.
Named CSS `gray` resolves to `#808080` and does not meet the 4.5:1 threshold on
either supplied row background.

| Foreground | Background | Ratio | AA | AAA |
|---:|---:|---:|---|---|
| <span class="color-swatch" style="--swatch: #808080" aria-hidden="true"></span>`#808080` | White `#FFFFFF` | 3.95:1 | Fail | Fail |
| <span class="color-swatch" style="--swatch: #808080" aria-hidden="true"></span>`#808080` | Stripe `#F7F7F7` | 3.69:1 | Fail | Fail |

## Related observations

- `darkgreen` (`#006400`) passes AA on both supplied backgrounds, but its
  6.94:1 ratio on `#F7F7F7` falls just below AAA for regular text.
- `brown` (`#A52A2A`) passes AA on both backgrounds, but its 6.61:1 ratio on
  `#F7F7F7` falls below AAA.
- `navy` at `opacity: 0.8` exceeds AAA in the supplied white and striped
  contexts.

These observations do not constitute a complete audit of every syntax-highlighting
palette. They show why the report must not claim site-wide AAA conformance based
only on the remediated link, opacity, and badge treatments.

## Recommended disposition

1. Correct `gray` upstream in the Publisher's generated syntax presentation.
2. Select a replacement against both white and `#F7F7F7`.
3. Decide whether these generated syntax colors target AA or the project's
   stronger AAA regular-text goal.
4. Add representative JSON, XML, TTL, and tree/table views to regression tests.

