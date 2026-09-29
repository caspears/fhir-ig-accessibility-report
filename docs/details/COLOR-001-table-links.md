# COLOR-001: Profile-Table and Site Links

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Content:** Regular text  
**Primary owner:** IG template CSS  
**Status:** Verified for the supplied representative contexts

## Problem

The original normal link color did not reach 4.5:1 on any supplied normal
background. The lowest observed ratio was 3.02:1 in the original
table-of-contents treatment. The original hover color met AA but not AAA.

## Source transition

The transition is present in `project.css`:

```diff
---link-color: #428bca;
+++link-color: #0000aa;

---link-hover-color: #2a6496;
+++link-hover-color: #000066;

---publish-box-bg-color: yellow;
+++publish-box-bg-color: #ffffcc;

---toc-box-bg-color: #ffeb7e;
+++toc-box-bg-color: #ffffcc;
```

The remediated stylesheet also assigns `#000066` to links inside the TOC box.

## Color preview

| Treatment | Preview and value |
|---|---|
| Original normal link | <span class="color-swatch" style="--swatch: #428BCA" aria-hidden="true"></span>`#428BCA` |
| AA candidate | <span class="color-swatch" style="--swatch: #346D9F" aria-hidden="true"></span>`#346D9F` |
| Implemented normal link | <span class="color-swatch" style="--swatch: #0000AA" aria-hidden="true"></span>`#0000AA` |
| Original hover link | <span class="color-swatch" style="--swatch: #2A6496" aria-hidden="true"></span>`#2A6496` |
| Implemented hover/focus link | <span class="color-swatch" style="--swatch: #000066" aria-hidden="true"></span>`#000066` |

## Contrast results

| Treatment | Foreground | Background | Ratio | AA | AAA |
|---|---:|---:|---:|---|---|
| Original normal | <span class="color-swatch" style="--swatch: #428BCA" aria-hidden="true"></span>`#428BCA` | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | 3.63:1 | Fail | Fail |
| Original normal | <span class="color-swatch" style="--swatch: #428BCA" aria-hidden="true"></span>`#428BCA` | Striped row <span class="color-swatch" style="--swatch: #F7F7F7" aria-hidden="true"></span>`#F7F7F7` | 3.39:1 | Fail | Fail |
| Original normal | <span class="color-swatch" style="--swatch: #428BCA" aria-hidden="true"></span>`#428BCA` | Original publication box <span class="color-swatch" style="--swatch: #FFFF00" aria-hidden="true"></span>`#FFFF00` | 3.38:1 | Fail | Fail |
| Original normal | <span class="color-swatch" style="--swatch: #428BCA" aria-hidden="true"></span>`#428BCA` | Original TOC box <span class="color-swatch" style="--swatch: #FFEB7E" aria-hidden="true"></span>`#FFEB7E` | 3.02:1 | Fail | Fail |
| Original hover | <span class="color-swatch" style="--swatch: #2A6496" aria-hidden="true"></span>`#2A6496` | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | 6.25:1 | Pass | Fail |
| Original hover | <span class="color-swatch" style="--swatch: #2A6496" aria-hidden="true"></span>`#2A6496` | Striped row <span class="color-swatch" style="--swatch: #F7F7F7" aria-hidden="true"></span>`#F7F7F7` | 5.83:1 | Pass | Fail |
| AA candidate | <span class="color-swatch" style="--swatch: #346D9F" aria-hidden="true"></span>`#346D9F` | Worst original context, <span class="color-swatch" style="--swatch: #FFEB7E" aria-hidden="true"></span>`#FFEB7E` | 4.55:1 | Pass | Fail |
| Implemented normal | <span class="color-swatch" style="--swatch: #0000AA" aria-hidden="true"></span>`#0000AA` | White <span class="color-swatch" style="--swatch: #FFFFFF" aria-hidden="true"></span>`#FFFFFF` | 13.29:1 | Pass | Pass |
| Implemented normal | <span class="color-swatch" style="--swatch: #0000AA" aria-hidden="true"></span>`#0000AA` | Striped row <span class="color-swatch" style="--swatch: #F7F7F7" aria-hidden="true"></span>`#F7F7F7` | 12.40:1 | Pass | Pass |
| Implemented normal | <span class="color-swatch" style="--swatch: #0000AA" aria-hidden="true"></span>`#0000AA` | Remediated box <span class="color-swatch" style="--swatch: #FFFFCC" aria-hidden="true"></span>`#FFFFCC` | 12.93:1 | Pass | Pass |
| Implemented hover/focus | <span class="color-swatch" style="--swatch: #000066" aria-hidden="true"></span>`#000066` | Remediated box <span class="color-swatch" style="--swatch: #FFFFCC" aria-hidden="true"></span>`#FFFFCC` | 17.14:1 | Pass | Pass |

The AA candidate is a reproducible proportional darkening of the original RGB
value that passes the supplied original backgrounds without rounding. WCAG does
not prescribe a unique replacement color, so it is an example of a minimal-AA
design choice rather than the only valid choice.

## Acceptance criteria

1. Normal and interaction-state links meet the selected contrast target in
   every normal context.
2. Links remain identifiable without relying solely on color where required.
3. Template CSS supplies the colors without postprocessing generated HTML.
