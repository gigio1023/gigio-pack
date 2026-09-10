---
name: python-coding-standards
description: >
  Use when writing, refactoring, or reviewing Python application or library
  code, choosing data types and enums, or splitting a large Python module.
  Applies repository-compatible typing, explicit StrEnum values, validation
  boundaries, cohesive modules, and focused tests. Uses the official external
  pydantic skill for Pydantic-specific modeling. NOT for docstring-only edits,
  a standalone formatting command, generated code unless explicitly in scope,
  or starting a plan or audit merely because Python files exist;
  gigio-review-results owns comparison of finished work against project intent.
---

# Python Coding Standards

Complete the requested Python change with clear types, stable external behavior, and modules whose responsibilities can be named. For review or diagnosis, return findings and their consequences without implementing them. A change request includes its relevant local checks; it does not imply a dependency migration, repository-wide cleanup, or publication.

## Start from the repository

Read the applicable project instructions, Python support range, dependency constraints, nearby implementation and tests, and configured checks before choosing syntax or tools. Existing public imports, accepted inputs, serialized values, and persisted data remain compatible unless the requested change includes a migration. An instruction to adopt a new style does not by itself authorize breaking those interfaces.

The rules here are fallbacks beneath the user's request and the repository's explicit decisions. Preserve the declared Python minimum and configured formatter, linter, type checker, and test runner. On a new project, choose a supported Python range that fits deployment and dependencies, and record it in project metadata and CI when setup is in scope. Do not turn a current interpreter version or preferred tool into an evergreen requirement.

## Types and data boundaries

Annotate public functions and interfaces, keep generic element types explicit, and contain `Any` where dynamic data enters. Use repository-supported syntax. Narrow a value or repair an inaccurate interface before adding a cast or suppression; a necessary suppression should identify the specific incompatibility and stay local.

Choose the representation by its job. Use a dataclass or ordinary class for internal state, `TypedDict` for a known dictionary shape, and `Protocol` for an interface whose implementation should remain independent. These types do not validate untrusted input at runtime. Use Pydantic when structured validation or serialization is needed and the dependency is already selected or justified by the requested work; do not add it to every internal object.

For Pydantic-specific work, load the official external `pydantic` skill as described in [Pydantic integration](references/pydantic-integration.md). That reference also records this pack's choices about input retention, enum representation, and compatibility. It is not a second Pydantic API guide.

Use standard-library `enum.StrEnum` for a closed string vocabulary that needs named runtime members, when the supported Python range permits it. Assign explicit values for API, database, event, configuration, and other persisted or transmitted tokens. Member names may change independently of those values; `auto()` must not make a public value depend on a Python identifier. Keep provider-extensible strings open unless a versioned schema actually defines a closed set. Read [types and enums](references/types-and-enums.md) for alternatives, older Python, and migrations from third-party `strenum`.

## Modules that remain easy to change

Keep related behavior with the module that owns its meaning. A useful split separates responsibilities, dependencies, or lifecycles and leaves a small interface between them. A class, helper, or extra layer should earn its place through state, an independent responsibility, or a useful boundary; neither one class per file nor one global `models.py` is a default architecture.

For a growing module, inspect the affected responsibilities before adding another one. As a local fallback, 500 handwritten first-party lines prompts a decomposition review; at 1,000, split at a meaningful boundary or explain why the module should stay together in the change summary. Repository limits win. These are review reminders, not automatic split rules, and they do not authorize unrelated restructuring. Generated files, vendored code, migrations, declarative tables, and cohesive test matrices need contextual review rather than automatic extraction.

Read [module boundaries](references/module-boundaries.md) before moving code between modules, changing public imports, or deciding how to split an oversized file. Preserve import direction and externally visible behavior; avoid a new runtime import cycle. A shorter file is not a successful refactor if understanding it requires more cross-file navigation.

## Correctness and verification

Keep error translation at a boundary where callers can act on it. Make resource ownership and async cancellation explicit. Read [correctness and testing](references/correctness-and-testing.md) when changing error handling, I/O, concurrency, or verification strategy.

Run the repository's checks relevant to the changed behavior. Public imports, accepted and rejected inputs, serialized fields and enum values, error behavior, and cleanup paths deserve focused compatibility tests when they change. Reuse tests that already establish the behavior; do not add tests that merely mirror helpers or satisfy a coverage quota. A formatter result cannot establish runtime correctness, and a type checker cannot establish external-data validation.

Finish when the requested result is implemented or reviewed and the relevant checks have run, or their exact limitation is reported. State the behavior changed, material compatibility or module decisions, checks and results, and anything not verified. Avoid inventing a plan file or a standard report template for ordinary Python work. Continue an already-requested publication through `draft-pr`, or an already-requested commit and push through `commit-and-push`.
