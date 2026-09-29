# Accessibility Checklist

[Before and After Results](07-before-after-results.md) · [Testing and Acceptance](03-testing-and-acceptance.md)

## How to read this page

This is a project checklist, not a conformance claim. **Pass** is reserved for
work with sufficient implementation and verification evidence. **Partial / Needs
Verification** means a remediation exists but testing or coverage is incomplete.

<div class="status-key">
  <span class="result result-pass">Pass</span>
  <span class="result result-fail">Open failure</span>
  <span class="result result-partial">Partial / Needs Verification</span>
  <span class="result result-untested">Not tested</span>
  <span class="result result-na">N/A</span>
</div>

## Addressed and verified

| Area | Evidence | Status |
|---|---|---|
| Skip navigation and primary-content target | Template and recursive remediation; representative target checks | <span class="result result-pass">Pass</span> |
| Heading hierarchy and numbering | Heading-level remediation and corrected CSS counters | <span class="result result-pass">Pass</span> |
| Decorative generated images | Recursive scan and remediation with no remaining anomalies | <span class="result result-pass">Pass</span> |
| Generated help and functional-image names | Help links and image/button ownership corrected | <span class="result result-pass">Pass</span> |
| Link contrast in supplied contexts | Measured against white, striped rows, and callout backgrounds | <span class="result result-pass">Pass</span> |
| Muted non-link and link contrast | Effective composited colors measured | <span class="result result-pass">Pass</span> |
| Red Must Support and green QA badges | Original AA and CDC enhanced AAA treatments documented | <span class="result result-pass">Pass</span> |

## Addressed but requiring broader verification

| Area | Remaining verification | Status |
|---|---|---|
| Tree expand/collapse controls | Screen-reader name/state announcements and all generated variants | <span class="result result-partial">Partial / Needs Verification</span> |
| Table-filter trigger and popup | Focus entry/return, Escape, checkbox operation, and page-family regression | <span class="result result-partial">Partial / Needs Verification</span> |
| Other generated buttons | “Show Usage,” “Show N more,” navigation collapse, and image-only variants | <span class="result result-partial">Partial / Needs Verification</span> |
| Complex authored diagrams | Confirm all unique figures have equivalent detailed descriptions | <span class="result result-partial">Partial / Needs Verification</span> |
| Link identification without color | Test surrounding-text cases and every interaction state | <span class="result result-partial">Partial / Needs Verification</span> |
| Generated profile-table semantics | Validate captions, header associations, reading order, and accessible names | <span class="result result-partial">Partial / Needs Verification</span> |

## Open findings

| Area | Required action | Status |
|---|---|---|
| Generated gray syntax comments | Replace `gray` with an AA-compliant treatment and test all syntax views | <span class="result result-fail">Open failure</span> |
| Duplicate IDs and parsing | Run validation, determine affected templates, and remediate safely | <span class="result result-untested">Not tested</span> |

## Not yet tested systematically

- Data-table header and cell associations across profile, QA, artifact, and
  comparison tables
- 200% text resize, 400% zoom, 320 CSS-pixel reflow, and table-region overflow
- Page titles, page language, and language changes
- Link purpose and distinguishability of repeated link text
- Focus order, focus return, and visible focus across every interactive variant
- DOM reading order and the result when styles are unavailable
- Consistent navigation and consistent identification across template families
- HTML validation and accessibility-tree verification
- Representative screen-reader/browser combinations
- Time-based media, timing, moving content, flashing, and form-validation
  requirements where applicable
- IG Publisher authoring-tool requirements and preservation of accessible
  information through generation

## Planned design exploration

The [Alternative Accessible Table Views](05-alternative-table-views.md) page
describes a Publisher-level tree view, simplified table, and text outline
generated from the same model. This is a proposed approach, not an implemented
remediation or a current Pass.
