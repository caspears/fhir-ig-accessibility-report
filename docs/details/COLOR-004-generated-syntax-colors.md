# COLOR-004: Generated Syntax Colors

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3 Contrast (Minimum); 1.4.6 Contrast (Enhanced)  
**Primary owner:** IG Publisher  
**Status:** Closed as not rendered in the supplied representative pages

## Initial observation

The supplied source contains JSON-template markup with comment separators such
as the following:

```html
<span style="color: Gray">//</span>
```

Named CSS `gray` resolves to `#808080`, which would not meet 4.5:1 on the
supplied white or striped backgrounds if the content were displayed.

| Foreground | Background | Ratio | AA | AAA |
|---:|---:|---:|---|---|
| <span class="color-swatch" style="--swatch: #808080" aria-hidden="true"></span>`#808080` | White `#FFFFFF` | 3.95:1 | Fail | Fail |
| <span class="color-swatch" style="--swatch: #808080" aria-hidden="true"></span>`#808080` | Stripe `#F7F7F7` | 3.69:1 | Fail | Fail |

## Source verification and disposition

In the representative CDC and HL7 profile pages, the entire `tabs-json` and
`tabs-xml` template block containing these spans is wrapped in an HTML comment:

```html
<!--
  <a name="tabs-json"></a>
  <div id="tabs-json">...
    <span style="color: Gray">//</span>
  ...</div>
-->
```

Parsing the pages as HTML produced no `color: Gray` elements in the rendered
DOM. The gray separators therefore are not visible text and are not an active
contrast failure in the supplied publications. This item should not appear as
an open remediation requirement.

If a future Publisher version enables this template, the contrast must be
retested before publication.

## Related observations for a future enabled view

- `darkgreen` (`#006400`) passes AA on both supplied backgrounds, but its
  6.94:1 ratio on `#F7F7F7` falls just below AAA for regular text.
- `brown` (`#A52A2A`) passes AA on both backgrounds, but its 6.61:1 ratio on
  `#F7F7F7` falls below AAA.
- `navy` at `opacity: 0.8` exceeds AAA in the supplied white and striped
  contexts.

These observations do not constitute a complete audit of every syntax-highlighting
palette.

## Regression protection

1. Test only rendered DOM content; do not treat text inside HTML comments as a
   user-visible contrast failure.
2. If JSON/XML template tabs are enabled, select colors against every actual
   background and meet the selected AA or enhanced AAA target.
3. Add representative JSON, XML, TTL, and tree/table views to regression tests.
