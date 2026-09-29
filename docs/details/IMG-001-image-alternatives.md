# IMG-001: Generated Image Alternatives

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Text alternatives  
**WCAG:** 1.1.1 Non-text Content  
**Primary owners:** IG Publisher, template, and IG authors  
**Status:** Existing publications remediated; upstream generation changes needed

## General rule

Every `<img>` needs an alternative that reflects its purpose in context:

- Use `alt=""` for a purely decorative or redundant image. This tells assistive
  technology to ignore it.
- Do **not** use `alt="."`, a filename, or placeholder punctuation. A period is
  announced as content and adds noise without conveying the image's purpose.
- For an image inside a functional link or button, put the accessible name on
  the link or button and normally give the nested image `alt=""`.
- For an informative image, describe the information or purpose—not its visual
  appearance alone. Include visible words when those words are not otherwise
  available as real text.
- For a complex diagram, provide a concise alternative that identifies the
  diagram and an adjacent detailed description conveying its relationships,
  sequence, decisions, and outcomes.

An image `title` attribute or tooltip is not a substitute for appropriate
alternative text. Conversely, repeating nearby text verbatim in `alt` can make
the page unnecessarily repetitive.

## Treatment by purpose

| Image category | Example | Required treatment |
|---|---|---|
| Decorative hierarchy structure | `tbl_spacer.png`, `tbl_vline.png`, `tbl_vjoin.png`, redundant `icon_*` | `alt=""`; do not use `alt="."` |
| Tree expand/collapse control | `tbl_vjoin-open.png`, `tbl_vjoin_end-open.png` | Native button with an action-specific accessible name and `aria-expanded`; nested image `alt=""` |
| Functional filter icon | `tree-filter.png` | Decorative nested image; accessible name on the button |
| Help-link icon | `help16.png` | Link named “How to read this table”; nested image `alt=""` |
| Information or warning icon | `information.png`, `icon-warning.png` | `alt=""` when adjacent text conveys the status; otherwise concise text such as “Information” or “Warning” on the owning control/status |
| External-link indicator | `external.png` | Decorative when adjacent link text and a consistent convention are sufficient; otherwise include the indication in the link's accessible name |
| QA/package decoration | Flame, package, dependency-tree connectors | `alt=""` when the package name and status letter/text convey the information |
| Decorative template graphic | `header_top.png` | `alt=""` or CSS background |
| Linked logo or brand image | CDC or organizational logo | Name the link's destination when the image is the link's only content; otherwise use `alt=""` beside equivalent brand text |
| Simple authored image | Screenshot or illustration conveying one idea | Concise alternative conveying the same purpose or information |
| Unique authored diagram | Process or architecture diagram | Meaningful short alternative plus an adjacent detailed description |

## Expand and collapse images

The original Publisher output places `onclick` directly on hierarchy images
and gives those images `alt="."`. Both parts require correction. The preferred
pattern is:

```html
<button type="button"
        class="tree-toggle"
        aria-expanded="true"
        aria-controls="tree-row-42-children"
        aria-label="Collapse children of DiagnosticReport.category">
  <img src="tbl_vjoin-open.png" alt="" aria-hidden="true">
</button>
```

When toggled, the script updates the controlled content, `aria-expanded`, and
the action in the accessible name. Enter and Space work automatically because
the control is a native button. The visual image is only decoration within
that button.

## Examples

```html
<!-- Decorative connector: ignored -->
<img src="tbl_vline.png" alt="">

<!-- Functional image: the button owns the name -->
<button type="button" aria-label="Choose table fields">
  <img src="tree-filter.png" alt="" aria-hidden="true">
</button>
```

## Acceptance criteria

1. Decorative images are ignored by assistive technology.
2. Functional controls derive their accessible name from the control, not a filename.
3. Meaningful image text is represented in the alternative.
4. Complex diagrams have an equivalent detailed description.
5. No generated image uses `alt="."`, filename text, or placeholder punctuation.
6. Expand/collapse state is exposed by the owning button rather than encoded in
   the image alternative.
