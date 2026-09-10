# Application Pitfalls

These are interpretation examples, not a supplied domain glossary or a universal banned-word list. Use the project's current definition and cited primary source.

| Condition | Tempting mistake | Correct application |
| --- | --- | --- |
| An internal phase has a familiar developer name | Present the phase as a standard research method | Preserve the code name where needed; describe what the phase actually does |
| A classifier returns a risk label | Say the system prevented the action | Distinguish detection, policy decision, and actual enforcement |
| A method combines training and parameter adaptation | Treat SFT, LoRA, reward source, and optimizer as interchangeable choices | Name each dimension and the actual update performed |
| Feedback changes the next prompt | Claim online learning or reinforcement learning | State what changed and whether a learned policy or parameters were updated |
| A metric name resembles another | Copy the label without checking its implementation | Keep the unit, denominator, calculation, attempt budget, and aggregation; AP and trapezoidal PR area need not match |
| A source reports a score or an oracle condition | Turn it into a proven upper bound | Preserve the reported scope; a bound needs assumptions and a supporting argument |
| A paragraph says reproducible, verified, or closed loop | Replace the phrase with another impressive label | Name the controlled conditions, performed check, or actual feedback path |
| A local preference prohibits a word in prose | Delete matching code strings or declare the term universally invalid | Apply the editorial preference to its stated surfaces and preserve protected literals |
| Several summaries repeat one claim | Count them as independent confirmation | Follow their source lineage to the original |
| A phrase looks awkward or synthetic | Attribute it to AI or mechanically rewrite every occurrence | Identify the semantic or reader problem and make the smallest supported correction |

A result stored as successful is not automatically correct, a verifier is not necessarily deterministic, and a model judge is not necessarily independent. Explain the procedure and what was actually checked rather than inferring guarantees from role names.
