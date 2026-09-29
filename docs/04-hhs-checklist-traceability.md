# HHS Checklist Traceability and Remaining Work

[Back to Start Here](index.md) · [Quick Reference](01-quick-reference.md)

## Purpose and limits

This page maps the supplied **HHS 508 Web Applications Checklist (03/2020)**
to this remediation report. It distinguishes a documented fix from a completed
conformance test. A blank or absent finding is not evidence of conformance.

The federal Section 508 web baseline incorporates WCAG 2.0 Level A and AA.
This project additionally chose AAA contrast for several regular-text
treatments. That stronger color target does not create a site-wide AAA claim.

## Current traceability

| HHS IDs | Topic | Current report evidence | Remaining action |
|---|---|---|---|
| 2A–2J | Text alternatives | [IMG-001](details/IMG-001-image-alternatives.md) covers decorative, functional, footer, and complex images | Inventory image maps, frames, CSS meaningful images, animation, CAPTCHA, and state-changing alternatives; mark each Pass or N/A |
| 3A–3G | Time-based media | None identified in representative pages | Confirm site-wide absence or test transcripts, captions, descriptions, and controls |
| 4A, 4J–4L | Structure and sequence | [HEAD-001](details/HEAD-001-heading-hierarchy.md) and [STRUCT-001](details/STRUCT-001-skip-navigation.md) | Verify lists, emphasis, DOM reading order, unstyled order, and popup placement |
| 4B–4I | Tables and forms | Keyboard behavior is documented in [KBD-001](details/KBD-001-table-controls.md) | Test table headers/associations/captions and all label, fieldset, legend, and multiple-label cases |
| 5A–5G | Color and distinguishability | COLOR-001 through COLOR-004 document measured contrast and an open syntax-color gap | Test non-text contrast, color-independent status, 200% resize, reflow, and images of text across page families |
| 6A–6E | Keyboard access | [KBD-001](details/KBD-001-table-controls.md) covers generated controls and popup behavior | Execute and record keyboard-only tests; include traps, event handlers, and shortcut conflicts |
| 7A–8A | Timing and flashing | No applicable feature documented | Confirm absence or test adjustable timing, moving/updating content, and flash thresholds |
| 9A–9C | Bypass blocks | [STRUCT-001](details/STRUCT-001-skip-navigation.md) | Verify every template family, including history, comparison, and QA variants |
| 9D–9K | Navigation and focus | Heading and keyboard pages provide partial evidence | Test titles, focus order/return, link purpose, multiple ways, informative labels, and visible focus |
| 10A–10B | Language | Not yet documented | Verify page-level `lang` and language changes in content/code examples |
| 11A–11D | Predictability | Filter popup behavior is partially documented | Test focus/input side effects and consistency of navigation and control names |
| 12A–12E | Input assistance | Filter input and checkboxes are the known inputs | Inventory all forms and test instructions, errors, suggestions, and prevention; mark inapplicable items explicitly |
| 13A | Parsing | Duplicate IDs were previously identified as a risk | Run HTML validation and duplicate-ID checks; document exceptions and ownership |
| 13B | Name, role, value | [KBD-001](details/KBD-001-table-controls.md) defines expected states | Verify in the accessibility tree and with a screen reader, including live state changes |
| 14A–14L | Software and authoring tools | Not covered by page remediation | Determine applicability to the IG Publisher as an authoring tool; assess template output, preservation of accessibility metadata, and prompts for authored content |

## Highest-risk omissions for an HL7/ONC request

1. **No requirement-to-evidence matrix at page level.** Record Pass, Fail,
   N/A, or Not Tested for each applicable HHS ID and representative page family.
2. **Tables need semantic testing, not only keyboard fixes.** Generated profile
   tables are complex and may require explicit header associations, captions,
   and accessible names.
3. **Dynamic state must be verified.** Tree controls and filter popups need
   correct name, role, expanded/checked state, focus movement, and announcement.
4. **Reflow and zoom need separate evidence.** Horizontal scrolling in dense
   FHIR tables may be acceptable within a data-table region, but the page as a
   whole must remain usable at zoom and narrow widths.
5. **Automated checks need a manual counterpart.** Axe or similar scanning will
   not establish keyboard behavior, meaningful alt text, reading order, or the
   correctness of complex-table relationships.
6. **The Publisher is an authoring tool.** If the request covers the tool—not
   just its HTML output—HHS 14H–14L require a separate applicability decision
   and evidence for accessible templates, preservation, and author guidance.
7. **The conformance target must be named.** Keep Section 508/WCAG 2.0 AA as a
   distinct baseline from voluntary WCAG 2.1/2.2 testing and from the selected
   AAA text-contrast design target.

## Evidence package needed for a full report

| Deliverable | Minimum contents |
|---|---|
| Scope statement | Versions, URLs, templates, Publisher build, page families, exclusions |
| Requirements matrix | HHS ID/WCAG criterion, applicability, result, page/sample, evidence link, owner |
| Remediation record | Before/after markup or CSS, rationale, upstream owner, historical-patch method |
| Test record | Browser/OS, viewport and zoom, keyboard steps, screen reader, automated tool/version |
| Issue register | Open finding, severity, affected output, workaround, planned upstream release |
| Regression plan | Publisher/template automated checks plus representative manual release gate |

## Suggested completion sequence

1. Close or formally accept COLOR-004.
2. Run a representative page-family matrix against every HHS ID.
3. Add semantic table, zoom/reflow, focus, language, title, links, parsing, and
   screen-reader results.
4. Mark genuinely absent features N/A with the evidence used to make that
   determination.
5. Separate output conformance from IG Publisher authoring-tool conformance.
6. Publish a dated snapshot with tool versions, open findings, and review sign-off.

## References

- Supplied `hhs-508-webapps-checklist.xlsx`, version 03/2020.
- [U.S. Access Board: Revised Section 508 Standards](https://www.access-board.gov/ict/)
- [U.S. Access Board: ICT Testing Baseline for Web](https://ictbaseline.access-board.gov/web-baselines/)
