# COLOR-003: Must Support and QA Status Colors

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Primary owner:** IG Publisher  
**Status:** Verified in the supplied representative profile pages

## Must Support badge

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

## QA dependency-status badge

The QA dependency table uses a white letter on an opaque green background.
The supplied HL7 screenshot uses `#008000`; the remediated CDC screenshot uses
`#006600`.

| Treatment | Badge background | Text | Ratio | AA | AAA |
|---|---|---:|---:|---|---|
| Original HL7 | <span class="color-swatch" style="--swatch: #008000" aria-hidden="true"></span>`#008000` | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | 5.14:1 | Pass | Fail |
| CDC enhanced | <span class="color-swatch" style="--swatch: #006600" aria-hidden="true"></span>`#006600` | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | 7.24:1 | Pass | Pass |

As with the red badge, the original treatment already satisfies the AA
minimum. The CDC treatment is an enhanced AAA text-contrast implementation.
The final upstream change should be verified against the generated CSS or
inline style; the values above were confirmed from the supplied rendered
screenshots.

## Color-independent meaning

The visible badge letter, its tooltip or accessible description, and
surrounding table semantics must continue to convey status without relying on
red or green alone.
