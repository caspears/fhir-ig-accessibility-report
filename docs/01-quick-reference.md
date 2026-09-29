# Section 508 Quick Reference

[Back to Start Here](index.md)

## Contrast thresholds

| Content | WCAG AA | WCAG AAA |
|---|---:|---:|
| Regular text | 4.5:1 | 7:1 |
| Large text | 3:1 | 4.5:1 |
| Meaningful non-text/UI components | 3:1 | No separate AAA threshold |

Contrast thresholds are not rounded. Each foreground treatment is evaluated
against every background on which it normally appears, including white and
alternating table-row backgrounds.

## Color, contrast, and opacity

| ID | Change | Backgrounds evaluated | AA-only position | Implemented target | Status | Details |
|---|---|---|---|---|---|---|
| COLOR-001 | Profile-table and site links | White; `#F7F7F7` rows; publication and TOC boxes; interaction states | A proportional-darkening candidate is `#346D9F`; other AA solutions are possible | `#0000AA`; hover/focus `#000066` | Verified for supplied contexts | [Table links](details/COLOR-001-table-links.md) |
| COLOR-002 | Muted table text and `opacity: 0.5` | White and `#F7F7F7` rows | For inherited `#333333` text, use at least `0.69`; muted links also require a darker link color | `opacity: 0.87` plus remediated link colors | Verified for supplied contexts | [Muted text and opacity](details/COLOR-002-muted-text-opacity.md) |
| COLOR-003 | Must Support and QA status badges | White text on opaque red and green backgrounds | Existing `#D50000` and `#008000` meet AA | `#B60000` and `#006600` meet AAA | Verified | [Must Support and QA status colors](details/COLOR-003-must-support-colors.md) |
| COLOR-004 | Inactive generated syntax template | White and `#F7F7F7` if enabled in the future | Retest if the commented-out template is enabled | No current change required | Closed: not rendered | [Generated syntax colors](details/COLOR-004-generated-syntax-colors.md) |

## Structure, images, and interaction

| ID | Area | Required result | Primary owner | Status | Details |
|---|---|---|---|---|---|
| STRUCT-001 | Skip navigation and main content | Keyboard users can bypass repeated navigation and focus the main content | Template | Implemented for published versions | [Skip navigation](details/STRUCT-001-skip-navigation.md) |
| HEAD-001 | Heading hierarchy | Page content begins with one appropriate H1 and continues in logical order | Publisher/template | Implemented through postprocessing | [Heading hierarchy](details/HEAD-001-heading-hierarchy.md) |
| IMG-001 | Generated image alternatives | Decorative images are hidden; meaningful and functional images have appropriate names | Publisher/template/IG author | Implemented with exceptions documented | [Image alternatives](details/IMG-001-image-alternatives.md) |
| KBD-001 | Generated table controls | Tree, filter, and disclosure controls operate from the keyboard and expose state | Publisher | Implemented through postprocessing | [Keyboard controls](details/KBD-001-table-controls.md) |

## Reading the status

- **Implemented for published versions:** Existing output was remediated.
- **Implemented through postprocessing:** New output is still generated with the
  issue and corrected afterward.
- **Upstream complete:** Publisher or template output is correct without
  remediation.
- **Pending source analysis:** CSS/HTML comparison is required before final
  ratios and selectors can be reported.
