# Medium and Figures

Use this when selecting a delivery form, converting an existing document, rendering a file, or commissioning figures. The document's purpose and information survive changes of medium.

## Respect the source and destination

Use the requested medium and existing source of truth. A Notion page, shared document, Markdown repository, or generated report may each be authoritative in its own workflow. Keep derived copies traceable to that source and update them through the established process.

For an existing Markdown-to-HTML project, edit the Markdown and rebuild the reading copy with its script. Do not hand-edit generated output. Do not create a second editable source simply because a different medium is convenient.

Choose the medium from the reader's use when none is specified. A quick memo needs a clear reading path; a broad comparison needs room for the data; a knowledge base needs navigation among maintained topics. A document does not automatically require a web page, application interface, or dashboard.

## Give visual reports an editorial point

A report explains a finding; an exploration tool helps investigate questions; an operational dashboard supports recurring monitoring. Choose the form the task needs. An interactive report still owes the reader a useful initial view and the author's supported interpretation. Filters and sortable tables do not replace that work.

Choose the comparison, relationship, distribution, or change that answers the main question. Give the decisive view visual priority and order supporting views by the questions it raises. Use emphasis and grouping to distinguish the main result from supporting material; equally prominent cards make readers rank the content themselves. A figure belongs because it explains something, not because a chart type or data column is available.

Make the important quantity visually comparable. Label axes with the actual measure and unit; use direct series labels when clearer than a detached legend. Avoid encoding one measure in bar length while presenting an unexplained second measure as the bar's value. Keep denominators, baselines, uncertainty, and meaningful contrary results visible where they affect the comparison.

Remove duplicate metric cards and charts that add no distinct comparison. Select and order table columns for the reader's task; complete row-level data can remain in an authorized detail view or attachment. Do not solve a clipped data dump by shrinking text. Use a consistent type scale, spacing, and color meaning. The dark default is a presentation preference, not a reason for neon accents, excessive panels, or arbitrary typography changes.

## Let controls explain themselves

Prefer familiar controls, descriptive labels, local state, and useful defaults over paragraphs explaining the interface. Essential unfamiliar help may be brief and adjacent to its control. Hover alone must not carry necessary interpretation or the only accessible instructions. If a custom symbol needs a long legend, simplify the encoding where the edit scope allows it.

An ordinary dated report does not need a paragraph announcing that it is a fixed snapshot. Display the relevant date or freshness state where needed. A real live-status expectation may justify a visible stale-data warning; do not hide that risk to make the page shorter.

When filters change the displayed population, make the active selection and any material denominator clear in the view. Captions, annotations, and derived claims must remain true for what is shown: update them, or keep them attached to a clearly separated fixed comparison. Do not retain a misleading caption and compensate with a paragraph saying that it describes a different view. Detailed interaction behavior belongs in authoring checks, not automatically in the reader-facing text.

Check the initial view without interaction, then the relevant filtered, empty, and selected states. Confirm that the reader can identify the important result and understand labels at the delivered size. A static or printed version must retain necessary findings and conditions without clicks; it need not reproduce every exploration control.

## Preserve meaning during conversion

Check that the destination retains the conclusions, conditions, sources, tables, figures, captions, and useful navigation. Reflow content for the destination instead of copying a layout that no longer reads well. Keep essential context visible when toggles, columns, hover text, or interactive controls do not transfer.

Inspect the actual rendered or published result. Check small text, clipped cells, contrast, page breaks where relevant, and access to linked material. A successful build or API response alone does not establish a complete readable document.

## Screen appearance defaults

Apply the entry point's dark screen default across the page and its figures. An adaptive page that follows the reader's operating-system theme is a separate requested choice; keep destination-controlled themes intact.

Use a dark canvas, light text, restrained neutral colors, and a limited accent palette. Share visual tokens across the page and its figures. Check contrast and legibility at the delivered size. A standalone figure needs an explicit background or a verified transparent treatment so it remains readable where it is embedded.

The previous report palette is available when useful: canvas `#0D0D0D`, body `#E6E6E6`, heading `#FFFFFF`, secondary text `#929591`, and an accent such as `#8386EB`. These are a reusable preset, not a requirement for unrelated formats. Do not vary palettes merely to make consecutive reports different.

## Medium-specific delivery

| Medium | Apply when producing it |
| --- | --- |
| Markdown | Use supported headings, tables, code, and links. Use expandable detail only where the renderer supports it. |
| HTML | Choose a readable width for the content; wide comparison views and narrower document pages have different needs. A shared offline file embeds required assets and avoids network dependencies. Check the intended browser and operating-system requirements. |
| Notion | Use native blocks through the authorized MCP or plugin, not browser automation for edits. Use tables, toggles, callouts, and columns when they help reading. Preserve existing child pages and databases. |
| Word, Google Docs, or PDF | Use the available document or PDF tooling. Check the actual document or export, including pagination, captions, and links. Preserve the editable source when one exists. |
| Other destinations | Use their supported structure and delivery tools while retaining the same content and source requirements. |

For Notion replacements, retrieve the page afterward and check the full changed content; partial writes have occurred. Stop a publication batch if corruption appears and repair the affected output. Notion controls page theme, so verify figure readability against its actual page background. If a specific template such as `notion-doc` is requested, use its available conventions within that request.

## Commission and inspect figures

Choose a figure for a real explanatory task: a mechanism, relationship, sequence, distribution, comparison, or change. Retain its question and important relationships when redrawing. Do not add unrelated components to fill empty space.

Use plain labels, stable terminology, and a clear reading order. State the finding in a title, caption, or adjacent sentence where it best serves the reader; do not repeat it in all three. A caption adds interpretation, a source, or a condition the figure needs, not a tour of clickable marks or a statement of what captions do. Number figures when readers need to reference them. Define unfamiliar encodings locally only when they cannot be made self-explanatory.

An organization or baseline belongs in a comparison when it is relevant and comparable data exists. Identify missing data instead of inventing a point. Keep explanatory analogies bounded by their literal mapping.

Use vector output where it suits the destination; provide a supported alternative when necessary. Avoid dense text diagrams as a substitute for a rendered figure. Fix small type, unnecessary whitespace, and crowded layouts inside the figure rather than relying only on a wider page.

When available, use `technical-diagram` or `mermaid-diagrams` for relationships, `data-chart` for measured data, and `drawio-diagram` for requested native files. State the destination, question, source data, language, and scheme in a figure request. Inspect the returned artifact rather than assuming the helper's defaults match.

The default for shared technical figures is established English terminology with Korean explanation in the surrounding Korean document. Follow the requested audience and language. Translate meaning and field usage, preserving numbers, units, product names, and API names; do not replace them with literal translations or invented labels.
