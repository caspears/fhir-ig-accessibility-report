# STRUCT-001: Skip Navigation and Main Content

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Page structure and navigation  
**WCAG:** 2.4.1 Bypass Blocks  
**Primary owner:** Template  
**Status:** Retrofitted to existing publications; template change implemented

## Problem

Keyboard users need a way to bypass repeated CDC and IG navigation and move
directly to the page content.

## Required structure

```html
<div id="skipmenu">
  <a class="skippy sr-only-focusable" href="#segment-content">
    Skip directly to site content
  </a>
</div>

<div id="segment-content" class="fhir-content" role="main" tabindex="-1">
  ...
</div>
```

If a native `<main>` can be generated safely, it is preferable to a `div` with
`role="main"`.

## Acceptance criteria

1. The skip link becomes visible when focused.
2. Activating it moves focus to the primary content.
3. `segment-content` occurs exactly once.
4. The page exposes one unambiguous main landmark.

