# Interaction, Evidence, and Verification

Read before building charts, slides, boards, editors, or exports. Add behavior only when it helps the user inspect, compare, or return useful information.

## Charts and diagrams

- Choose the encoding from the question: line for time, bars or dots for categories, a bullet-style comparison for actual versus target, slopegraph for paired change, or a table when exact values matter most. Shared-scale small multiples often beat overlapping series.
- Prefer inline SVG for modest static graphics. Include a `viewBox`, readable labels, accessible title/description, surrounding figure/caption, and a data table or equivalent textual account. A canvas-only chart needs an accessible alternative.
- Keep bars and area magnitudes on an honest baseline; label any transformed or truncated scale and choose a non-length encoding if a zero baseline obscures the relevant difference. Show units, denominators, time periods, exclusions, uncertainty, and missing data as appropriate.
- Do not confuse absence with zero, interpolation with observation, projections with actuals, or correlation with causation. Derived metrics must agree with supplied values and a stated calculation.
- Use color purposefully, with text, shape, or pattern alternatives. Aim for at least 4.5:1 contrast for normal text, 3:1 for large text, and 3:1 for meaningful control/graphic boundaries where applicable. Test the actual foreground/background pairs rather than trusting token names.
- Perform an eraser pass for redundant marks and a collision pass for overlapping labels, lines, and annotations. Remove redundancy without erasing units, uncertainty, or needed navigation.
- If a chart library is explicitly requested, inspect its actual API and bundle permitted assets for offline use. Do not claim an external CDN is self-contained. Do not silently load an executable third-party script.

## Decks and presentations

Use slide jobs such as framing, model, evidence, options, risks, and next decision only as the content needs them. Do not force a fixed count or compulsory interactive visual. Claim-led headings must remain supported, not become slogans that outrun the evidence.

Start with readable document sections. Enable paging only after script initialization succeeds. Add Previous/Next buttons, current slide count, and optional labeled slide selectors. Inactive slides should not contain reachable hidden focus targets. Keep focus predictable after navigation and announce the new slide without reading the entire deck.

Arrow-key navigation must ignore typing in inputs, textareas, selects, or editable content. Do not intercept browser shortcuts or trap Tab. Disable boundary buttons or make looping explicit. Fullscreen requires user activation, a working fallback, and honest failure feedback.

Do not force fixed-height frames at the expense of overflow: use a scrollable document on small or short viewports and with enlarged text. Respect `prefers-reduced-motion`. For print, show every slide in order with sensible page breaks; include important secondary material, and hide controls. Never leave only the active slide printable. If notes are included, make their inclusion/exclusion explicit, but remember they are not private simply because hidden onscreen.

## Editors, boards, and exports

- Keep original input distinct from current working state. Use stable IDs rather than labels as keys. Filters change visibility, not the underlying dataset; exports should clearly declare whether they contain all items or only the filtered view.
- Use native buttons, selects, labeled fields, and validation messages. Boards need keyboard alternatives to drag operations. Include empty/filter-no-match states where applicable and a deliberate reset path when edits can be discarded.
- A preview must render text safely. Test HTML-like strings, quotes, newlines, Unicode, and script-closing text as literal values, not executable markup. Prompt substitution must never use `eval` or function construction.
- Downloads can serialize current state using a Blob and an object URL. Include a meaningful filename, format, and version if the user will import it elsewhere. Release object URLs after use without revoking them before the download starts.
- Clipboard APIs may be absent or denied in local files and browser sandboxes. Feature-detect, await success, handle rejection, and provide a selectable-text or download fallback. "Copied" is shown only after success. Apply the same discipline to fullscreen and other permission-sensitive APIs.
- Local edits normally disappear on reload. State this clearly. Add browser storage only when requested and appropriate; it is neither secure storage nor cross-device persistence and can be blocked. Never store credentials or silently send edits to a host.

## Browser check matrix

Use the host's installed browser tools and artifact conventions rather than assuming a specific command or service. Run checks on the file that will actually be delivered.

| State | Exercise | Evidence to capture |
|-------|----------|---------------------|
| Wide layout | Open artifact at a representative desktop viewport | Inspect a screenshot: hierarchy, charts, density, labels, no clipping |
| Narrow/zoomed | Use a phone-width viewport and enlarged text | Inspect overflow, reading order, tables, touch targets, controls |
| Keyboard | Tab through controls; activate with native keyboard behavior | Focus is visible, order is sensible, hidden content not focusable, no traps |
| Non-default | Navigate slides, open details, move an item, edit input, or filter | State actually changes; label and result agree; empty/invalid states work |
| Export | Change state, download/copy it, inspect the actual payload | Current values preserved, scope correct, unsafe text stays literal |
| Failure | Deny clipboard/fullscreen or supply invalid input if used | No false success, clear recovery or fallback |
| No network | Check requests and block network during reload | No runtime dependency; approved source hyperlinks do not auto-load |
| No JavaScript | Disable scripting and reload if using enhancement | Core report remains readable; interactive-only capability has an explanation |
| Print | Emulate print or inspect a generated PDF | All essential sections/slides/details visible, controls hidden, no clipping |

Also inspect console/page errors and verify numeric claims directly against source values. Automated checks and screenshots complement one another: a screenshot cannot establish that a download contains the right data, and a passing DOM check cannot establish readable layout.

Report only checks actually run, including viewport/state coverage and remaining limitations. Do not claim a complete accessibility audit or cross-browser certification from a single browser pass.
