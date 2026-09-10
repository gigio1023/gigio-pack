# Company Names and Local Meanings

Use this reference when a term may be a company name, product name, internal component, or company-specific use of a familiar industry expression. Keep the list small and tied to encountered work. The task is to learn the user's conventions, not to make every internal label conform to external vocabulary.

## Separate the kinds of usage

| Kind | Treatment |
| --- | --- |
| Proper name for a company, product, or project | Preserve the confirmed spelling and referent. Do not infer a technical definition or silently repair an unusual spelling |
| Familiar term used locally for a component, team, mode, or workflow | Record the local meaning separately from the industry meaning and specify the audience where the local shorthand is appropriate |
| General industry term | Use the relevant external definition and conditions; do not invent a local exception to excuse an unsupported claim |
| Unconfirmed usage | Keep the observed spelling and context, ask what it refers to, and leave the interpretation pending |

The same string may have both a local and a general meaning. For example, `PII` or `topic model` might be used as a company's component label in a particular document; the name alone does not establish what the component does. These are ambiguity examples, not asserted definitions for any company.

## Ask only what remains unresolved

Read the existing internal-name map, prior user answers, and the relevant owning document or code before asking. When the referent, intended meaning, spelling, or audience remains ambiguous, ask the user one concise question or a small related batch. Show the actual phrase and enough context to make the question answerable. Offer plausible interpretations only when supported by the material; allow the user to supply a different meaning. Do not turn a few local exceptions into a lengthy interview.

A useful question is: “In this document, does ‘topic model’ name an internal component? What does it take as input and produce, and should that name remain in customer-facing text?” For a proper name, confirm the referent and exact spelling only if those are unclear. Do not ask all of these questions when an existing record already settles them.

This is clarification of meaning, not an approval request. Continue independent work while waiting. Until answered, preserve the name and mark the interpretation as unconfirmed; do not replace it with the industry's definition or silently treat a suggested meaning as accepted. Ask again only when new contradictory information or a materially changed context makes the recorded answer insufficient.

## Record and apply the answer

In the project's existing internal-name map, record the exact name and useful aliases, kind of usage, local meaning or referent, organizational or product scope, contrast with the general meaning when relevant, internal/external wording, and the dated user confirmation or owning source. Distinguish user-confirmed intended meaning from implementation verified in code. A user's naming decision establishes the convention; it does not prove capability, compliance, accuracy, or deployment.

For internal readers, use the confirmed local name naturally. For external or mixed readers, preserve a public proper name and briefly explain an ambiguous local term at first use; use the confirmed external wording when the company has one. Do not expose a private alias or its explanation outside the existing sharing scope. Correct misleading claims around a legitimate name rather than renaming the name itself.

Source exclusions for general wording do not erase local conventions: an internal document can locate a company label without becoming evidence of industry usage. Treat generated internal prose as a candidate to verify with the user or owning implementation. Keep company records in the project; do not copy real company names or unconfirmed definitions into the reusable public skill.
