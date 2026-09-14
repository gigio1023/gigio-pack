# Medium and Figures

Use this when selecting a delivery form, converting an existing document, rendering a file, or commissioning figures. The document's purpose and information survive changes of medium.

## Respect the source and destination

Use the requested medium and existing source of truth. A Notion page, shared document, Markdown repository, or generated report may each be authoritative in its own workflow. Keep derived copies traceable to that source and update them through the established process.

For an existing Markdown-to-HTML project, edit the Markdown and rebuild the reading copy with its script. Do not hand-edit generated output. Do not create a second editable source simply because a different medium is convenient.

Choose the medium from the reader's use when none is specified. A quick memo needs a clear reading path; a broad comparison needs room for the data; a knowledge base needs navigation among maintained topics. A document does not automatically require a web page, application interface, or dashboard.

## Preserve meaning during conversion

Check that the destination retains the conclusions, conditions, sources, tables, figures, captions, and useful navigation. Reflow content for the destination instead of copying a layout that no longer reads well. Keep essential context visible when toggles, columns, hover text, or interactive controls do not transfer.

Inspect the actual rendered or published result. Check small text, clipped cells, contrast, page breaks where relevant, and access to linked material. A successful build or API response alone does not establish a complete readable document.

## Screen appearance defaults

The author's established preference is a dark scheme for screen documents and figures when their styling is under our control. Use light when requested or needed for print; a destination with its own theme retains that behavior. An adaptive page is a separate requested choice.

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

Use plain labels, stable terminology, a clear reading order, and a caption that explains the takeaway and material conditions. Number figures when readers need to reference them. Keep definitions or interpretive guidance close enough that the figure can be understood without reconstructing the drafting session.

An organization or baseline belongs in a comparison when it is relevant and comparable data exists. Identify missing data instead of inventing a point. Keep explanatory analogies bounded by their literal mapping.

Use vector output where it suits the destination; provide a supported alternative when necessary. Avoid dense text diagrams as a substitute for a rendered figure. Fix small type, unnecessary whitespace, and crowded layouts inside the figure rather than relying only on a wider page.

When available, use `technical-diagram` or `mermaid-diagrams` for relationships, `data-chart` for measured data, and `drawio-diagram` for requested native files. State the destination, question, source data, language, and scheme in a figure request. Inspect the returned artifact rather than assuming the helper's defaults match.

The default for shared technical figures is established English terminology with Korean explanation in the surrounding Korean document. Follow the requested audience and language. Translate meaning and field usage, preserving numbers, units, product names, and API names; do not replace them with literal translations or invented labels.
