# Before and After Results

[Accessibility Checklist](06-accessibility-checklist.md) · [Technical Findings](01-quick-reference.md)

## Assessment basis

**Before** means existing, unmodified HL7 IG Publisher/template output.
**After** means the proposed upstream Section 508/WCAG AA minimum. Where CDC
implemented a stronger AAA text-contrast treatment, that enhancement is noted
in the details and does not redefine the upstream minimum.

This is a working assessment. “Not tested” is not a Pass, and “N/A” requires
scope confirmation before a final conformance report is issued.

Compact evidence markers in the details column link to the exact remediation
section. Hovering a marker displays a short description. The same marker may
appear in several rows when one remediation supports multiple requirements.

| Marker | Detailed evidence |
|---|---|
| <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#general-rule" title="Image purpose, alternative-text rules, and prohibited placeholder alternatives">IMG</a> | Image alternatives and functional-image treatment |
| <a class="evidence-ref" href="../details/KBD-001-table-controls/#generated-control-examples" title="Native buttons, tree controls, filter popup, checkboxes, and keyboard behavior">KBD</a> | Generated control semantics and keyboard operation |
| <a class="evidence-ref" href="../details/HEAD-001-heading-hierarchy/#required-result" title="Page heading hierarchy and numbering requirements">HEAD</a> | Heading hierarchy |
| <a class="evidence-ref" href="../details/STRUCT-001-skip-navigation/#required-structure" title="Skip link and main-content target implementation">SKIP</a> | Bypass navigation |
| <a class="evidence-ref" href="../details/COLOR-001-table-links/#contrast-results" title="Link contrast before, AA candidate, and CDC enhanced treatment">C1</a> | Link contrast |
| <a class="evidence-ref" href="../details/COLOR-002-muted-text-opacity/#non-link-inherited-text" title="Opacity compositing and muted text contrast">C2</a> | Muted and inherited text |
| <a class="evidence-ref" href="../details/COLOR-003-must-support-colors/#qa-dependency-status-badge" title="Red Must Support and green QA badge contrast">C3</a> | Status badges |
| <a class="evidence-ref" href="../05-alternative-table-views/#proposed-user-experience" title="Tree, simplified-table, and text-outline presentation proposal">ALT</a> | Alternative table presentations |

<div class="status-key">
  <span class="result result-pass">Pass</span>
  <span class="result result-fail">Fail</span>
  <span class="result result-partial">Partial / Needs Verification</span>
  <span class="result result-untested">Not tested</span>
  <span class="result result-na">N/A</span>
</div>

## Best practices

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 1A | Provide an alternate where content cannot otherwise conform | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Proposed simplified table and text-outline views require implementation and equivalence testing. <a class="evidence-ref" href="../05-alternative-table-views/#conformance-cautions" title="Requirements and cautions for an equivalent alternate presentation">ALT</a> |
| 1B | Supply the appropriate checklist for linked or embedded files | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Inventory downloadable documents and linked attachments. |

## 1.1 Text alternatives

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 2A | Images, image buttons, and image-map hotspots have concise alternatives | <span class="result result-fail">Fail</span> | <span class="result result-pass">Pass</span> | Generated functional images now derive names from links or buttons; meaningful images receive alternatives. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#treatment-by-purpose" title="Treatment matrix for decorative, functional, informative, and complex images">IMG</a> |
| 2B | Decorative images use null alternatives or CSS | <span class="result result-fail">Fail</span> | <span class="result result-pass">Pass</span> | Recursive remediation assigns `alt=""` or presentation treatment to decorative images and prohibits `alt="."`. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#general-rule" title="Why decorative images use a null alternative and placeholder punctuation is prohibited">IMG</a> |
| 2C | Complex images have equivalent detailed descriptions | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Representative diagrams were described; complete authored-image inventory remains. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#general-rule" title="Short alternatives and adjacent detailed descriptions for complex diagrams">IMG</a> |
| 2D | Embedded multimedia is identified in accessible text | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm that scoped IG publications contain no embedded multimedia. |
| 2E | Frames have appropriate titles | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence of frames and iframes in scope. |
| 2F | Content hidden from everyone is also hidden from assistive technology | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test collapsed trees, popups, responsive navigation, and hidden tab panels. |
| 2G | Meaningful CSS background images have text alternatives | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Inventory template and Publisher background images. |
| 2H | Animated content has an alternative or description | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence of meaningful animation. |
| 2I | CAPTCHAs are accessible | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No CAPTCHA identified in static IG output. |
| 2J | Alternatives update when element state changes | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Tree and filter controls require synchronized names and `aria-expanded`; verify announcements. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#expand-and-collapse-images" title="Expand/collapse image conversion to a stateful native button">IMG</a> <a class="evidence-ref" href="../details/KBD-001-table-controls/#tree-row-disclosure" title="Tree disclosure semantics and synchronized state">KBD</a> |

## 1.2 Time-based media

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 3A | Time-based media worksheet requirements are satisfied | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm no media appears in scoped publications. |
| 3B | Transcript for prerecorded audio-only content | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence. |
| 3C | Transcript or audio description for prerecorded video-only content | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence. |
| 3D | Synchronized captions for prerecorded audio | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence. |
| 3E | Transcript or audio description for prerecorded video | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence. |
| 3F | Synchronized captions for live multimedia | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | Static IG publication does not provide live multimedia. |
| 3G | Audio descriptions for applicable video | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence. |

## 1.3 Adaptable

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 4A | Semantic markup identifies headings, lists, and specialized text | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Heading hierarchy corrected; lists, emphasis, code, abbreviations, and blockquotes still need systematic review. <a class="evidence-ref" href="../details/HEAD-001-heading-hierarchy/#required-result" title="Required page heading hierarchy and numbering result">HEAD</a> |
| 4B | Tables are used for tabular data with separate data cells | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Audit generated and template tables for layout-table misuse. |
| 4C | Data-table headers are identified | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Proposed alternate views use explicit table headers; current generated tables require audit. <a class="evidence-ref" href="../05-alternative-table-views/#simplified-table" title="Semantic structure proposed for the simplified table">ALT</a> |
| 4D | Data cells are associated with their headers | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Test complex profile, QA, comparison, and artifact tables. <a class="evidence-ref" href="../05-alternative-table-views/#simplified-table" title="Header and row structure proposed for the simplified table">ALT</a> |
| 4E | Captions and summaries are used where appropriate | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Add accessible table names or captions where visual context is insufficient. <a class="evidence-ref" href="../05-alternative-table-views/#simplified-table" title="Caption and accessible-name guidance for the simplified table">ALT</a> |
| 4F | Layout tables identify purpose and omit structural table markup | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Inventory legacy template layout tables. |
| 4G | Labels are associated with form inputs | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Filter input, popup checkboxes, and view selector need associated labels in every variant. <a class="evidence-ref" href="../details/KBD-001-table-controls/#table-filter-popup" title="Native labeled checkboxes in the filter popup">KBD</a> <a class="evidence-ref" href="../05-alternative-table-views/#proposed-user-experience" title="Labeled view-selection controls">ALT</a> |
| 4H | Related controls use fieldset and legend | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Use grouping for filters and the proposed view selector; verify generated markup. <a class="evidence-ref" href="../05-alternative-table-views/#proposed-user-experience" title="Fieldset and legend example for the view selector">ALT</a> |
| 4I | Multiple labels are presented in a meaningful order | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test filter and search labels, help text, and descriptions. |
| 4J | Reading and navigation order is logical | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Keyboard changes help, but full DOM and screen-reader order require testing. |
| 4K | Meaningful CSS-generated content remains available without styles | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Inspect pseudo-elements, heading numbering, status badges, and tree graphics. |
| 4L | Popups and dynamic content occur inline with their triggers | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Filter popup is being associated with its trigger; verify DOM placement and reading order. <a class="evidence-ref" href="../details/KBD-001-table-controls/#table-filter-popup" title="Filter trigger, controlled popup, and checkbox structure">KBD</a> |
| 4M | Instructions do not rely on shape, size, or location | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Review authored narrative and generated help. |
| 4N | Instructions do not rely on sound | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No sound-based instructions identified. |

## 1.4 Distinguishable

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 5A | Color is not the sole means of conveying information | <span class="result result-partial">Partial / Needs Verification</span> | <span class="result result-partial">Partial / Needs Verification</span> | Badge letters supplement color; audit remaining status, flag, and validation presentations. <a class="evidence-ref" href="../details/COLOR-003-must-support-colors/#color-independent-meaning" title="Status remains available through badge text and semantics, not color alone">C3</a> |
| 5B | Links are distinguishable without relying only on color | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Link colors and states were changed; generated-page contexts and non-color differentiation need full verification. <a class="evidence-ref" href="../details/COLOR-001-table-links/#acceptance-criteria" title="Link contrast and non-color identification acceptance criteria">C1</a> |
| 5C | Meaningful non-text graphics do not rely only on color | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Review authored charts, diagrams, badges, and icons. |
| 5D | Automatically playing audio can be controlled | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No autoplay audio identified. |
| 5E | Regular text reaches at least 4.5:1 contrast | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | [Links](details/COLOR-001-table-links.md), [muted text](details/COLOR-002-muted-text-opacity.md), and [badges](details/COLOR-003-must-support-colors.md) are corrected; a broader rendered-content audit remains. The gray syntax markup is [not rendered](details/COLOR-004-generated-syntax-colors.md). CDC enhanced colors target AAA. |
| 5F | Page remains readable and functional at 200% text size | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test every representative page family; include dense tables and navigation. |
| 5G | Images of text are avoided when real text can provide the presentation | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Footer text has an alternative; replace with real text when template design permits and inventory other cases. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#treatment-by-purpose" title="Footer image and other image-of-text treatments">IMG</a> |

## 2.1 Keyboard accessible

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 6A | All functionality is keyboard available | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Tree, filter, and disclosure controls remediated; comprehensive keyboard regression remains. <a class="evidence-ref" href="../details/KBD-001-table-controls/#keyboard-behavior-matrix" title="Expected keyboard behavior for generated controls">KBD</a> |
| 6B | Shortcuts do not conflict with browser or assistive-technology keys | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm no custom access keys or page shortcuts exist. |
| 6C | Functionality does not require timed keystrokes | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test popup and disclosure handlers. |
| 6D | Device-dependent event handlers are avoided | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Replace click-only image handlers with native controls and keyboard-independent events. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#expand-and-collapse-images" title="Replacement of clickable hierarchy images with native buttons">IMG</a> |
| 6E | Keyboard focus is never trapped | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Test filter popup, responsive navigation, tabs, generated controls, and alternative views. <a class="evidence-ref" href="../details/KBD-001-table-controls/#acceptance-criteria" title="Keyboard and focus acceptance criteria">KBD</a> |

## 2.2 Enough time and 2.3 Seizures

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 7A | Time limits can be disabled, adjusted, or extended | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No time limits identified in static output. |
| 7B | Moving, blinking, or scrolling content can be paused or hidden | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence of applicable content. |
| 7C | Automatically updating content can be paused or manually controlled | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence of automatic refresh or updating regions. |
| 8A | Content does not exceed flash thresholds | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm absence of flashing content. |

## 2.4 Navigable

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 9A | A link bypasses repeated navigation and page elements | <span class="result result-fail">Fail</span> | <span class="result result-pass">Pass</span> | Skip link and focusable main-content target added to templates and existing publications. <a class="evidence-ref" href="../details/STRUCT-001-skip-navigation/#required-structure" title="Skip link and primary-content target markup">SKIP</a> |
| 9B | Proper heading structure can provide an additional bypass mechanism | <span class="result result-fail">Fail</span> | <span class="result result-pass">Pass</span> | Content H1 and hierarchy corrected; skip link remains available. <a class="evidence-ref" href="../details/HEAD-001-heading-hierarchy/#required-result" title="Corrected content heading hierarchy">HEAD</a> <a class="evidence-ref" href="../details/STRUCT-001-skip-navigation/#acceptance-criteria" title="Skip-navigation acceptance criteria">SKIP</a> |
| 9C | Frames are titled when used as the bypass mechanism | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No frames identified. |
| 9D | Page title is descriptive and informative | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test all generated families, including history, QA, comparison, JSON, and XML pages. |
| 9E | Focus/navigation order is logical | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Control remediation supports order, but page-level testing remains. <a class="evidence-ref" href="../details/KBD-001-table-controls/#keyboard-behavior-matrix" title="Expected tab and focus behavior for generated controls">KBD</a> |
| 9F | Focus moves to and returns from menus, dialogs, and popups appropriately | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Filter popup design specifies focus entry, Escape, and return; verify implementation. <a class="evidence-ref" href="../details/KBD-001-table-controls/#table-filter-popup" title="Filter popup focus entry, closing, and return behavior">KBD</a> |
| 9G | Link purpose is clear from text or programmatic context | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Empty and image-only generated links were addressed; audit repeated and ambiguous links. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#treatment-by-purpose" title="Accessible names for image links and functional icons">IMG</a> |
| 9H | Same-text links to different targets are distinguishable | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Review repeated “history,” “details,” “here,” and icon links. |
| 9I | At least two ways are available to locate pages | <span class="result result-partial">Partial / Needs Verification</span> | <span class="result result-partial">Partial / Needs Verification</span> | Navigation, TOC, artifact listing, and search exist; verify coverage and operation. |
| 9J | Headings and control labels are informative | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Heading levels and generated control names improved; test duplicate and context-dependent labels. <a class="evidence-ref" href="../details/HEAD-001-heading-hierarchy/#acceptance-criteria" title="Heading hierarchy acceptance criteria">HEAD</a> <a class="evidence-ref" href="../details/KBD-001-table-controls/#preferred-implementation" title="Accessible naming requirements for generated controls">KBD</a> |
| 9K | Keyboard focus is visibly apparent | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Focus styling exists; verify clipping, contrast, and visibility for every generated control. <a class="evidence-ref" href="../details/KBD-001-table-controls/#preferred-implementation" title="Visible-focus requirement for generated controls">KBD</a> |

## 3.1 Readable and 3.2 Predictable

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 10A | Page language is identified | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Verify the `html` `lang` attribute across all templates and standalone pages. |
| 10B | Language changes are identified | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Review authored narrative, terminology, quoted material, and examples. |
| 11A | Receiving focus does not unexpectedly change context | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test navigation, tabs, popups, filters, and proposed view selector. |
| 11B | Input does not unexpectedly change context without warning | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Table filters intentionally change display; label behavior and preserve predictable focus. <a class="evidence-ref" href="../details/KBD-001-table-controls/#table-filter-popup" title="Expected behavior of filter inputs and popup controls">KBD</a> |
| 11C | Repeated navigation remains in consistent order | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Compare all template/page families. |
| 11D | Controls with the same function are identified consistently | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Normalize accessible names for expand/collapse, help, filter, and disclosure controls. <a class="evidence-ref" href="../details/KBD-001-table-controls/#other-generated-disclosures" title="Shared native-button pattern for generated disclosures">KBD</a> |

## 3.3 Input assistance

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 12A | Required formats, values, and lengths are described | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm that scoped pages contain no data-entry forms beyond search/filter controls. |
| 12B | Validation errors are clear and provide access to the problem | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Static QA validation messages are content, not user form-validation errors; confirm scope. |
| 12C | Controls receive sufficient labels, cues, and instructions | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Add explicit labels and grouped instructions for filters and alternate-view controls. <a class="evidence-ref" href="../details/KBD-001-table-controls/#table-filter-popup" title="Labels and grouping for filter controls">KBD</a> <a class="evidence-ref" href="../05-alternative-table-views/#proposed-user-experience" title="Legend and labels for presentation selection">ALT</a> |
| 12D | Detected errors receive timely correction suggestions | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No applicable data-entry workflow identified. |
| 12E | Legal, financial, or test-data changes are reversible or confirmed | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | Static IG pages do not change such data. |

## 4.1 Compatible

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 13A | Significant HTML validation and parsing errors are avoided | <span class="result result-fail">Fail</span> | <span class="result result-untested">Not tested</span> | Duplicate IDs and generated-markup validity remain unresolved risks; run validation and regression tests. |
| 13B | Custom controls expose name, role, value, state, and changes | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Native-button conversion and ARIA state are designed; verify accessibility-tree and screen-reader output. <a class="evidence-ref" href="../details/KBD-001-table-controls/#generated-control-examples" title="Native control markup and synchronized ARIA state">KBD</a> |

## Software and authoring tools

| HHS ID | Failure condition | Before | After | Failure details, changes, or remaining work |
|---|---|---|---|---|
| 14A | Users control platform accessibility features | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Determine applicability to Publisher command-line and generated web output. |
| 14B | Application does not interrupt platform accessibility features | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Requires authoring-tool scope and interoperability testing. |
| 14C | Text and attributes are rendered and programmatically determinable | <span class="result result-untested">Not tested</span> | <span class="result result-partial">Partial / Needs Verification</span> | Native HTML and controls improve determinability; complete assessment remains. |
| 14D | Customized font, color, type, and contrast preserve content | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test user styles, forced colors, high contrast, zoom, and text spacing. |
| 14E | Any alternative interface meets applicable standards | <span class="result result-na">N/A</span> | <span class="result result-partial">Partial / Needs Verification</span> | Becomes applicable if simplified and outline views are implemented. <a class="evidence-ref" href="../05-alternative-table-views/#conformance-cautions" title="Conformance requirements for alternate table presentations">ALT</a> |
| 14F | Caption controls are at the same level as volume controls | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No media player identified. |
| 14G | Audio-description controls are at the same level as volume controls | <span class="result result-na">N/A</span> | <span class="result result-na">N/A</span> | No media player identified. |
| 14H | Authoring tools can create accessible output | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Publisher/template and postprocessors address several issues; native accessible generation remains incomplete. <a class="evidence-ref" href="../05-alternative-table-views/#upstream-disposition" title="Why the accessible renderers belong in the Publisher">ALT</a> |
| 14I | Conversion preserves supported accessibility information | <span class="result result-untested">Not tested</span> | <span class="result result-untested">Not tested</span> | Test preservation of authored alt text, headings, labels, language, captions, and table semantics. |
| 14J | Generated PDFs conform to PDF/UA when supported | <span class="result result-untested">Not tested</span> | <span class="result result-na">N/A</span> | Confirm whether the Publisher creates PDFs within the assessed scope. |
| 14K | Authoring tools prompt authors to create accessible content | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | Add validation or guidance for alt text, complex descriptions, heading use, tables, and language. <a class="evidence-ref" href="../details/IMG-001-image-alternatives/#acceptance-criteria" title="Image-alternative acceptance criteria suitable for Publisher validation">IMG</a> |
| 14L | Supplied templates satisfy accessibility requirements | <span class="result result-fail">Fail</span> | <span class="result result-partial">Partial / Needs Verification</span> | CDC templates improved; base/HL7 templates require upstream remediation and complete testing. <a class="evidence-ref" href="../details/STRUCT-001-skip-navigation/#required-structure" title="Template-level skip-navigation structure">SKIP</a> <a class="evidence-ref" href="../details/HEAD-001-heading-hierarchy/#required-result" title="Template and Publisher heading requirements">HEAD</a> |
