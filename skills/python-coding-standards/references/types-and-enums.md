# Types and Enums

Read this when selecting a data representation, replacing string constants, or changing enum values. Follow the repository's supported Python range and public interfaces before applying a fallback.

## Choose the representation

| Need | Usually fits | Limit |
| --- | --- | --- |
| Closed, named string values used at runtime | `enum.StrEnum` | Python 3.11+; values must remain stable when persisted or transmitted |
| Closed values used only in annotations | `Literal` | No runtime validation by itself; useful for discriminators when a schema requires literals |
| Values an external provider may extend | `str` or a validated value object | Validate documented syntax without silently narrowing an open vocabulary |
| Nominal distinction between same-shaped identifiers | `NewType` | A static distinction, not runtime validation or a runtime class |
| Opaque named values that should not compare as strings | `Enum` | Use an explicit conversion when an external representation is needed |
| Internal data with named fields and optional behavior | Dataclass or ordinary class | Frozen data is not necessarily deeply immutable or hashable |
| An existing dictionary with a known shape | `TypedDict` | The runtime value remains a dictionary |
| A structural interface between implementations | `Protocol` | Introduce it for a real interface or test boundary, not merely to wrap a class |

Use built-in generic annotations and union syntax only when the Python minimum permits them. Parser syntax such as Python 3.12's `type Alias = ...` cannot be backported by importing `typing_extensions`. Check runtime annotation consumers before changing forward references or `from __future__ import annotations`.

## Keep enum values stable

The following example separates internal member names from external values:

```python
from enum import StrEnum


class JobState(StrEnum):
    QUEUED = "queued"
    RUNNING = "running"
    SUCCEEDED = "succeeded"


def parse_job_state(raw: str) -> JobState:
    return JobState(raw)


assert parse_job_state("queued") is JobState.QUEUED
assert JobState.QUEUED.value == "queued"
```

Parse strings at the input boundary and use members consistently inside typed code. Unknown closed-set values should produce the boundary's documented error, not be mapped to a plausible success or active state. If unknown values must survive forwarding, represent that requirement explicitly rather than coercing them into an enum.

At output, emit the defined value through `.value` or a serializer whose behavior is verified. `StrEnum` is a `str` subclass, but an API that requires exactly `str` may need `str(member)` or `.value`. String operations on a member return ordinary strings. Member names, repr output, and incidental enum iteration order are not substitutes for an external schema.

`auto()` is appropriate only when the concrete value has no external meaning. With standard-library `StrEnum`, it lowercases the member name. A rename can therefore change stored data without an obvious string edit.

## Compatibility changes

Before replacing an enum implementation or value, inspect API payloads, database mappings, configuration, event consumers, generated schemas, and existing fixtures that depend on it. Preserve old accepted values until the requested migration defines how readers and writers move. Where a transition accepts legacy spellings, keep acceptance aliases separate from the canonical output and test both. A Python enum alias alone does not define a producer/consumer rollout or database migration.

Distinguish `from enum import StrEnum` from `from strenum import StrEnum`. The third-party package's base `StrEnum` preserves member-name case for `auto()`, while the standard-library class lowercases it. Do not replace the import without checking actual values. For Python below 3.11, preserve the repository's existing approach; an explicit `class Status(str, Enum)` can represent string values, but its `str()` and formatting behavior are not automatically identical to standard-library `StrEnum`.

## Sources and local choices

Checked 2026-09-10. These sources establish language behavior; representation choices and stable-value requirements above are this pack's policy.

- [Python enum reference](https://docs.python.org/3/library/enum.html): member names and values, `StrEnum`, `auto()`, exact-string caveat, and version-dependent membership behavior. Construct the enum to parse a value instead of relying on containment behavior across Python versions.
- [Python typing reference](https://docs.python.org/3/library/typing.html): `Literal`, `NewType`, `TypedDict`, `Protocol`, and annotation-version requirements.
- [Python dataclasses reference](https://docs.python.org/3/library/dataclasses.html): generated methods, frozen instances, and hashing conditions.
- [Third-party StrEnum reference](https://strenum.readthedocs.io/en/latest/api_ref.html): the separate package's value-generation behavior.

Recheck the affected API when the repository changes its Python support range or enum implementation. The checked date is not a requirement to browse for every Python edit.
