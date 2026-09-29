# COLOR-003: Must Support and Status Colors

[Back to Quick Reference](../01-quick-reference.md)

**Category:** Color and contrast  
**WCAG:** 1.4.3, 1.4.6, and 1.4.11 as applicable  
**Primary owner:** IG Publisher/template CSS  
**Status:** Sample based on known remediation values

## Known color transitions

```diff
-color: green;
+color: #006600;

-color: red;
+color: #B60000;
```

The actual report will identify the exact selectors and whether each color is
used for regular text, a badge background, an icon, or another non-text object.

## Illustrative white-background comparison

| Use | Treatment | Color | Ratio on white | AA regular text | AAA regular text |
|---|---|---:|---:|---|---|
| Green text | Original | `#008000` | 5.14:1 | Pass | Fail |
| Green text | Implemented | `#006600` | 7.24:1 | Pass | Pass |
| Red text | Original | `#FF0000` | 4.00:1 | Fail | Fail |
| Red text | Illustrative minimum AA | `#EE0000` | 4.53:1 | Pass | Fail |
| Red text | Implemented | `#B60000` | 7.03:1 | Pass | Pass |

These values do not establish compliance on striped rows or colored badges.
Those combinations will be added after computed backgrounds are resolved.

## Color-independent meaning

Must Support and status information must not be communicated by color alone.
Visible text, symbols, labels, or programmatic names must continue to express
the status when colors cannot be distinguished.

