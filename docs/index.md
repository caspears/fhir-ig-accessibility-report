# FHIR IG Section 508 Accessibility Remediation

> **Working remediation record:** Verified values are based on the supplied
> original and modified CSS plus representative generated HTML. Open items are
> identified explicitly and are not counted as conformant.

## Purpose

This report documents accessibility problems identified in generated FHIR
Implementation Guide pages, the remediation applied to existing publications,
and the upstream changes needed in the IG Publisher and templates.

The report focuses on Section 508 accessibility. CDC deployment/security
requirements, CSS framework conflicts, and CDC header/footer integration are
documented separately and are not classified as accessibility findings unless
they directly affect an accessibility requirement.

## Navigate this report

- [508 quick reference](01-quick-reference.md)
- [Color and contrast method](02-color-contrast-method.md)
- [Testing and acceptance](03-testing-and-acceptance.md)
- [HHS checklist traceability and remaining work](04-hhs-checklist-traceability.md)
- [Alternative accessible table views](05-alternative-table-views.md)
- [Accessibility checklist](06-accessibility-checklist.md)
- [Before and after results](07-before-after-results.md)

## Scope

The accessibility work is grouped into:

1. Color, contrast, and opacity
2. Page structure and skip navigation
3. Heading hierarchy
4. Images and alternative text
5. Keyboard operation and focus
6. Testing and regression protection

## Conformance language

This report identifies whether a particular presentation meets an applicable
WCAG success criterion. It does not claim that the entire site conforms to
WCAG Level AAA merely because selected text colors meet the enhanced contrast
criterion.
