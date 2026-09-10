# Example: Standing Terminology Instructions

Adapt this example to the project's paths and requested authority before adding it to the actual instruction entry point. The example grants both application and in-scope maintenance; omit the maintenance grant if only ongoing use was requested. Relative paths below are examples to replace and verify, not files supplied by this skill.

```markdown
## Terminology and expressions

- At the start of every task, read `terminology.md` and the relevant topic and anti-pattern entries. Use `use-terminology` to apply them throughout responses, research, writing, reviews, and code explanations, even when the task does not mention wording.
- Use established English research and developer terms first; explain their contextual meaning in the project's working language. Distinguish general usage, source-specific definitions, internal names, and editorial preferences. Preserve the definition's conditions and level of claim.
- Correct confirmed terminology misuse, unsupported coined names, and overstated claims in directly managed documents encountered or edited during the task. This is standing authorization for those local corrections and the related definition and expression records through `curate-terminology`; do not wait for another correction request. An explicit read-only task limits the result to findings and proposed corrections.
- Preserve quotations, collected originals, historical records, code identifiers, APIs, schemas, and data labels. Correct surrounding explanations or add a dated correction. Follow the relevant code-change process for identifier changes. External edits and publication require their existing service authorization; record inaccessible-source corrections locally within the authorized scope.
- Verify changed definitions against primary sources using the glossary's source-maintenance rules. Correct the glossary itself when it is wrong, record recurring cases in its anti-pattern document, and leave unresolved meaning explicit. Do not treat the glossary as more authoritative than the source it summarizes.
- Apply these rules to material encountered in the task; do not sweep every repository. Record material corrections and affected files, and run the project's existing index and document checks when files or navigation change.
```
