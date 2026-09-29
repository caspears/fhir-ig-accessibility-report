# KBD-001: Generated Table Controls

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Keyboard access, name/role/value, and focus  
**Primary owner:** IG Publisher  
**Status:** Existing publications remediated with postprocessing

## Affected controls

- Tree expand/collapse images
- Table-filter popup trigger
- Filter checkboxes
- “Show Usage” and “Show N more” disclosures
- Navigation collapse button

## Preferred implementation

Generate native `<button type="button">` controls. Retain visual images as
decorative children when needed.

Each disclosure control should provide:

- keyboard activation with Enter and Space;
- an accessible name identifying the action or affected row;
- `aria-expanded` synchronized with the visual state;
- `aria-controls` where a stable target exists;
- a visible focus indicator; and
- predictable focus movement when a popup opens or closes.

## Acceptance criteria

1. Every control is reachable in a logical Tab order.
2. Enter and Space activate controls as expected.
3. Filter checkboxes toggle using Space.
4. Escape closes the filter popup and returns focus to its trigger.
5. Name, role, and state are exposed to accessibility APIs.

