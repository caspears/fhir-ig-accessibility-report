# Testing and Acceptance

[Back to Start Here](index.md) · [Quick Reference](01-quick-reference.md)

## Required evidence

| Test area | Evidence |
|---|---|
| CSS transition | Exact original and modified declarations or unified diff |
| Contrast | Foreground, effective background, opacity, ratio, and AA/AAA outcome |
| Keyboard | Tab, Enter, Space, and Escape behavior on representative controls |
| Semantics | Accessibility tree or screen-reader confirmation of name, role, and state |
| Structure | Heading outline, landmarks, skip target, and duplicate-ID check |
| Images | Decorative, functional, simple, and complex-image review |
| Regression | Representative generated pages and automated tests |

## Representative page families

- Home/content page
- Profile key-elements, differential, and snapshot tables
- Definitions, mappings, examples, and testing pages
- JSON and XML rendered pages
- Change-history and comparison pages
- Table of contents and artifact listing
- Publisher QA pages, documented separately when not public-facing

## Completion criteria

A change is complete when:

1. A newly generated publication is correct without the corresponding
   postprocessor.
2. The result is verified on all representative page families.
3. The lowest normal contrast combination meets the selected threshold without
   rounding.
4. Automated regression coverage exists where practical.
5. Historical-publication remediation remains available and documented.

