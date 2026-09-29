# IMG-001: Generated Image Alternatives

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Text alternatives  
**WCAG:** 1.1.1 Non-text Content  
**Primary owners:** IG Publisher, template, and IG authors  
**Status:** Existing publications remediated; upstream generation changes needed

## Treatment by purpose

| Image category | Example | Required treatment |
|---|---|---|
| Decorative generated structure | `tbl_*`, redundant `icon_*` | `alt=""` |
| Functional filter icon | `tree-filter.png` | Decorative nested image; accessible name on the button |
| Help-link icon | `help16.png` | Link named “How to read this table”; nested image `alt=""` |
| Decorative template graphic | `header_top.png` | `alt=""` or CSS background |
| Footer image containing organization text | `footer.png` | `alt="National Center for Emerging and Zoonotic Infectious Diseases"` |
| Unique authored diagram | Process or architecture diagram | Meaningful short alternative plus an adjacent detailed description |

## Acceptance criteria

1. Decorative images are ignored by assistive technology.
2. Functional controls derive their accessible name from the control, not a filename.
3. Meaningful image text is represented in the alternative.
4. Complex diagrams have an equivalent detailed description.

