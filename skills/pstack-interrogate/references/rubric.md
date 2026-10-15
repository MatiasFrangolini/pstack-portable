# Review rubric

Apply relevant lenses, preserving the user's intended behavior and scope.

- Correctness: empty and invalid inputs, failures, state transitions, lifecycle, retries, idempotency, races, and real outputs.
- Root cause: trace the symptom across callers and ownership to the first wrong decision. If the triggering state is legitimate, handling it with a guard or validation can be the actual fix. If the state should never exist, find its producer; a guard or retry that hides it leaves the defect unresolved. Judge the demonstrated contract rather than rejecting defensive checks mechanically.
- Contracts: API and persistence compatibility, runtime validation, permissions, tenant/site isolation, and independent deployments.
- Structure: ownership, interface depth, representation leaks, temporal coupling, duplicate decisions, and mutable state.
- Verification: observable behavior, correct negative paths, integration gaps, and proof that the measured work happened.
- Complexity: actual callers and requirements, justified indirection, dead paths, and speculative options.
- Security: a concrete input path through authentication/authorization to the relevant sink or exposed data. Do not invent an attacker or capability.

A finding names the trigger, actual bad result, execution path, tight source location, practical severity, and evidence. A concern without that chain stays unproven. A valid assertion of absence or an empty result is not automatically a weak test.
