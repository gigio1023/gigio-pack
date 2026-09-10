# Research Expressions in Context

Read this when researching how practitioners describe a concept, operation, or project. Source eligibility is defined in [source verification](source-verification.md); this reference defines what to extract from eligible material. Capture useful affirmative language as well as anti-patterns. Store the expression entries in the relevant documents under the consuming project's `docs/terminology/`; register and cite each supporting source in `docs/terminology/references.md`.

## Extract more than names

| Surface | What to record |
| --- | --- |
| Terms and distinctions | Accepted name, meaning, neighboring concepts, and the actual boundary between them |
| Verbs and collocations | Who performs the action, the verb and its object, required conditions, and what the verb does or does not imply |
| Sentence patterns | How the source states a capability, limitation, comparison, dependency, result, or uncertainty |
| Project explanation | The problem addressed, intended users, core abstraction, responsibilities of components, data/control flow, lifecycle, and explicit non-goals |
| Claim strength | Whether the sentence describes a design goal, implemented behavior, observed measurement, hypothesis, or proven result |

Read the concept explanation, operational guide, and relevant maintainer blog together when they answer different parts of the question. Track the relationship between words and the actual system: a command name, a controller's action, and a user's goal may use different verbs. Do not collect synonyms detached from the actor or object.

A concise expression record contains the source passage or a short attributed excerpt, URL and section/version, the actor–verb–object pattern, its contextual meaning, a reusable example or paraphrase, and conditions where reuse would mislead. Keep excerpts short and preserve exact quotations separately from adaptations. Explain in Korean when that is the project's working language; retain the English expression as the primary form.

## Worked reading examples

The [Kubernetes controller explanation](https://kubernetes.io/docs/concepts/architecture/controller/) describes a control loop in terms of current state and desired state. Extract which component observes or changes which resource and how the document explains their relationship. Do not turn a one-time check into a controller merely by borrowing its verbs.

The [Helm chart documentation](https://helm.sh/docs/topics/charts/) connects packaging, a chart's files, and Kubernetes resources. Extract what is packaged, configured, or deployed and how those objects differ. This page carried a Helm-version migration warning when inspected on 2026-09-10; check the applicable version before adopting operational wording. These are examples of reading source language in context, not a glossary that overrides the project's implementation.

For a paper and its author blog, compare how the paper defines the method with how the blog explains its motivation and operation. Record useful verbs and explanatory structure from both, but keep the paper's assumptions, experimental scope, and uncertainty in the adopted description. A compelling blog explanation does not strengthen the paper's result.

## Apply with semantic fit

An accepted pattern is reusable because its underlying relation fits, not because it sounds professional. Preserve the actual actor, action, object, and scope. Avoid copying branded vocabulary, rhetorical intensity, or a project-wide architecture into an unrelated system. If representative sources disagree, record the distinct contexts and prefer a concrete description over a newly coined umbrella phrase.
