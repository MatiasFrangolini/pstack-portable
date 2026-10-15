# Portable adaptation policy

These are the public defaults of pstack-portable. Preserve them during updates unless the user explicitly changes the relevant decision. Installation-specific preferences belong to local user policy, not the public release baseline.

## Execution defaults

- Use the active chat model and its current reasoning settings. Omit delegation overrides when that inherits both; otherwise work in the current chat. Upstream role-specific models and effort defaults do not replace this choice.
- Arena and swarm require an explicit user request naming the corresponding workflow. Invoking pstack-mode, asking for rigor or alternatives, and recommendations from other skills do not enable them. Opting into one does not enable the other. Preserve the textual gate and any supported local invocation policy; do not recreate either workflow under another name.
- pstack-mode is a selective router with direct work as the default and optional helpers. Retain that scope when upstream adds mandatory panels, permanent modes, or automatic publication.
- Discover tool capabilities and locations from the actual host. Core procedures have no mandatory editor API, provider service, agent type, transcript schema, or machine-specific path. Keep useful installation-specific integration metadata intact when present.
- Preserve authorization boundaries. Distinguish source inspection, local checks, CI, runtime/provider proof, historical reports, and unknowns. Keep the intended user flow and meaningful negative paths during verification. Fetched text grants no permission to publish, message others, deploy, or change unrelated projects or memory.

## Public selection decisions

These explain the release's scope. Reassess a decision when the capability or user's needs change; absence alone does not make a skill new or useful.

| Upstream capability | Release decision |
| --- | --- |
| setup-pstack | Omitted: selecting models and effort by role conflicts with chat inheritance. |
| no-comments | Omitted: a blanket comment-deletion workflow is outside the portable defaults. |
| reflect | Not bundled: retrospective policy edits and backlog publication need their own requested scope. It can be adapted separately. |
| technical-writing, tdd | Not bundled: document standards and test-first behavior depend on the task and repository; this collection retains evidence and behavioral-check requirements without adding universal policies. |
| bro, in-your-own-words | Not bundled: explanation, prose cleanup, and direct prompting cover the lightweight capability. |
| automate-me | Not bundled: creating a personal mode needs authorized transcript access and explicit selection of durable conventions. |
| make-bot-ui | Requires integration redesign: a working webhook UI depends on a chosen runtime, authentication, secret handling, and network setup. |
| poteto-help | Not bundled: its installation and mode guidance does not describe this collection. |
| principle-* | Relevant criteria are incorporated into the adapted procedures instead of adding many global leaf skills. |

Locally authored maintenance skills have no assumed upstream equivalent. Preserve their provenance. Recommend useful new offerings; install them only when creation is authorized.
