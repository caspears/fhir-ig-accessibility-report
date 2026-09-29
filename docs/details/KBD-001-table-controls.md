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

## Generated-control examples

### Tree row disclosure

```html
<button type="button"
        class="tree-toggle"
        aria-expanded="false"
        aria-controls="tree-42-children"
        aria-label="Expand children of category">
  <img src="tbl_spacer.png" alt="" aria-hidden="true">
</button>
<div id="tree-42-children" hidden>...</div>
```

The button—not its image—owns the accessible name and state. The script must
toggle both `hidden` and `aria-expanded` from the same source of truth.

### Table-filter popup

```html
<button type="button"
        class="table-filter-trigger"
        aria-expanded="false"
        aria-controls="table-filter-17">
  Filter table columns
  <img src="tree-filter.png" alt="" aria-hidden="true">
</button>
<div id="table-filter-17" role="group" aria-label="Columns to display" hidden>
  <label><input type="checkbox" checked> Bindings</label>
  <label><input type="checkbox" checked> Constraints</label>
  <label><input type="checkbox" checked> Obligations</label>
</div>
```

The checkboxes remain native controls, so Tab reaches them and Space changes
their checked state. Opening the popup moves focus to its first checkbox;
Escape closes it and returns focus to the trigger. Clicking outside may also
close it, but must not be the only closing method.

### Other generated disclosures

Apply the same pattern to “Show Usage,” “Show N more,” navigation collapse,
and any image-only expander: native button, accessible name, synchronized
`aria-expanded`, stable controlled target, Enter/Space activation, and visible
focus. Do not add `role="button"` to an image or link when a real button can be
generated.

## Keyboard behavior matrix

| Control | Tab | Enter | Space | Escape | Focus after close |
|---|---|---|---|---|---|
| Tree disclosure | Reaches button | Toggle | Toggle | Not required | Remains on button |
| Filter trigger | Reaches button | Open/close | Open/close | Close when open | Trigger |
| Filter checkbox | Reaches each checkbox | Browser-dependent; do not require | Toggle checked state | Close popup | Trigger |
| “Show Usage” / “Show N more” | Reaches button | Toggle | Toggle | Not required | Remains on button |
| Collapsed navigation | Reaches button | Toggle | Toggle | Close when open | Trigger |

## Acceptance criteria

1. Every control is reachable in a logical Tab order.
2. Enter and Space activate controls as expected.
3. Filter checkboxes toggle using Space.
4. Escape closes the filter popup and returns focus to its trigger.
5. Name, role, and state are exposed to accessibility APIs.
