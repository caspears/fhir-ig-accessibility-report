# HEAD-001: Page Heading Hierarchy

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Structure and relationships  
**Primary owner:** IG Publisher and base template  
**Status:** Corrected through postprocessing; native support preferred

## Problem

Generated content historically began at `<h2>`, leaving pages without an
appropriate content-level `<h1>`. Correcting the tags also required aligning
the Publisher heading-number counters and level-specific color rules.

## Required result

- The principal page heading uses `<h1>`.
- Subsections follow a logical hierarchy without level changes made merely for
  visual styling.
- Heading numbering remains sequential.
- Level-specific color rules apply to the intended heading level.
- The Publisher honors the configured `page-heading-level` parameter.

## Acceptance criteria

1. Every representative content page has an appropriate H1.
2. Automated numbering agrees with the visible hierarchy.
3. Heading links and anchors remain stable.
4. Code examples containing heading text are not rewritten.

