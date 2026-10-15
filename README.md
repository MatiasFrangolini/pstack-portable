# pstack-portable

21 portable engineering skills: 20 adapted from [Lauren Tan's pstack](https://github.com/cursor/plugins/tree/main/pstack) and one selective maintenance workflow.

Use the model and reasoning settings already active in your chat. Discover the tools your harness actually provides. Keep parallel candidate generation and coverage opt-in. Preserve local adaptations when upstream changes.

This is an unofficial MIT-licensed adaptation. See [credits and provenance](CREDITS.md).

## Install with NPX

Use the same open skills installer used by other GitHub skill collections:

```sh
npx skills@latest add MatiasFrangolini/pstack-portable
```

The installer lets you choose the skills and supported agents. Its default scope is the current project. To install globally:

```sh
npx skills@latest add MatiasFrangolini/pstack-portable --global
```

Inspect the collection or select a single skill:

```sh
npx skills@latest add MatiasFrangolini/pstack-portable --list
npx skills@latest add MatiasFrangolini/pstack-portable --skill pstack-mode
```

Node.js/npm and source access are needed for this optional installer. The skill instructions themselves require no Node runtime. For manual installation, copy the desired folders under `skills/` into your harness's documented skill directory. If automatic discovery is unavailable, ask your agent to read the selected `SKILL.md` directly.

The [skills CLI documentation](https://github.com/vercel-labs/skills#readme) describes supported agents and installation options. Installation support does not establish equivalent agent behavior across harnesses.

## Use

```text
Use pstack-mode to investigate this bug, make the smallest justified fix,
and verify the real behavior.

Use pstack-update, audit only, to compare this installation with upstream.

Use pstack-mode with arena and swarm for this task.
```

`pstack-mode` chooses optional procedures that fit the request. It does not activate `pstack-arena` or `pstack-swarm` unless you explicitly request the corresponding workflow. Requesting one does not enable the other. Each skill also enforces this gate in its own instructions. If your harness offers explicit-only discovery settings, enable them for those two skills as well; such host metadata is not required by the portable core.

The other procedures can be called directly. Missing sibling skills are handled through the stated capability fallback; the collection has no mandatory dependency on an external review, testing, PR, or retrospective skill.

## What changed from upstream

All adapted skills preserve the active chat model and reasoning settings, discover available tools, respect the user's authorization, and distinguish verified results from assumptions. They do not select provider-specific models or start publication just because a workflow was invoked.

Compared against [upstream 0.15.25 at e5136d8](https://github.com/cursor/plugins/tree/e5136d82418d2db3165ea1050d17577cd618cc05/pstack). The per-skill metadata retains the original adaptation source.

| Upstream | Included skill | Main adaptation or limitation |
| --- | --- | --- |
| poteto-mode | [pstack-mode](skills/pstack-mode/SKILL.md) | Selective router; direct work by default; arena/swarm explicit-only; no permanent editor mode or automatic shipping. |
| how | [pstack-how](skills/pstack-how/SKILL.md) | Trace a concrete flow with available tools; direct exploration for narrow questions; no mandatory editor subagents. |
| why | [pstack-why](skills/pstack-why/SKILL.md) | Discover relevant evidence sources; keep confidence and coverage explicit; no fixed connector set. |
| blast-radius | [pstack-blast-radius](skills/pstack-blast-radius/SKILL.md) | Prove the critical compatibility assumptions with available code/runtime evidence; no mandatory panel. |
| architect | [pstack-architect](skills/pstack-architect/SKILL.md) | Compare consequential designs when useful; preserve consumers; model diversity is not supplied by inherited-model workers. |
| arena | [pstack-arena](skills/pstack-arena/SKILL.md) | Explicit-only candidate comparison; inherited-model workers or labeled sequential self-review; original cross-model diversity is lost. |
| swarm | [pstack-swarm](skills/pstack-swarm/SKILL.md) | Explicit-only bounded coverage; discovered concurrency/resource controls; sequential fallback when delegation is unavailable. |
| interrogate | [pstack-interrogate](skills/pstack-interrogate/SKILL.md) | Evidence-based adversarial judgment; inherited-model reviewers or labeled self-review; no cross-model diversity or automatic fixes. |
| benchmark-checklist | [pstack-benchmark-checklist](skills/pstack-benchmark-checklist/SKILL.md) | Host-appropriate counters, fair repeated measurements, correctness checks, and noise-aware conclusions. |
| recall | [pstack-recall](skills/pstack-recall/SKILL.md) | Discover authorized history access; reconcile with current artifacts; no fixed transcript directory or schema. |
| create-verification-skill | [pstack-create-verification-skill](skills/pstack-create-verification-skill/SKILL.md) | Generate and execute a project-specific recipe using existing controls; prove usable startup and preserve evidence. |
| maintain-verification-skill | [pstack-maintain-verification-skill](skills/pstack-maintain-verification-skill/SKILL.md) | Source and live coverage audit; repair owned verification material; product changes and publication remain separately scoped. |
| figure-it-out | [pstack-figure-it-out](skills/pstack-figure-it-out/SKILL.md) | Small verifiable experiments; test a shared premise after repeated failures; no perpetual loop or automatic PRs. |
| show-me-your-work | [pstack-show-me-your-work](skills/pstack-show-me-your-work/SKILL.md) | Portable append-only TSV evidence trail; no automatic commit/publication or dependence on one transcript format. |
| correct | [pstack-correct](skills/pstack-correct/SKILL.md) | Structural enforcement for demonstrated recurring mistakes; scoped proof rather than global policy edits after every correction. |
| typescript-best-practices | [pstack-typescript-best-practices](skills/pstack-typescript-best-practices/SKILL.md) | Target actual domain and boundary risks; retain runtime authorization/concurrency checks; avoid blanket syntax or brand migrations. |
| teach | [pstack-teach](skills/pstack-teach/SKILL.md) | Explain from source and evidence in the user's language; no required quiz or particular visualization provider. |
| unslop | [pstack-unslop](skills/pstack-unslop/SKILL.md) | Requested prose editing that preserves facts, uncertainty, and voice; no always-on replacement for user style. |
| ketchup | [pstack-ketchup](skills/pstack-ketchup/SKILL.md) | Read-only current-chat catch-up with available artifacts; preserve local/CI/runtime distinctions; no required visual service. |
| sharpen | [pstack-sharpen](skills/pstack-sharpen/SKILL.md) | Improve the approach, then execute; preserve explicit constraints; use a proportional outside check without mandatory extra reviewers. |
| No assumed counterpart | [pstack-update](skills/pstack-update/SKILL.md) | Selective upstream maintenance with provenance, local fingerprints, backups, and recommendations for useful new skills. |

## Not bundled and why

Some capabilities are portable but outside this collection's defaults. Others need runtime integrations to preserve their original behavior.

| Upstream capability | Status | Reason |
| --- | --- | --- |
| setup-pstack | Intentionally omitted | Per-role model/effort selection conflicts with inheriting the current chat settings. |
| no-comments | Intentionally omitted | A blanket comment-deletion workflow is not a default engineering policy here. |
| reflect | Could be adapted separately | Retrospective policy edits and backlog publication require their own requested scope. |
| automate-me | Could be adapted separately | A personal mode needs authorized history and selection of conventions for that installation. |
| technical-writing, tdd | Intentionally omitted | Writing standards and test-first behavior are task/repository decisions; this release avoids another universal policy. |
| bro, in-your-own-words | Lightweight overlap | Explanation, prose cleanup, and direct prompting cover the useful capability. |
| poteto-help | Replaced by this README | Original installation and mode assumptions do not describe this collection. |
| principle-* | Incorporated selectively | Relevant criteria live in the adapted procedures instead of many additional global leaf skills. |
| make-bot-ui | Requires integration redesign | Webhooks, bot runtime, authentication, secret handling, and network setup are not reproduced by portable instructions alone. |
| Benny automation pack | Requires integration redesign | Issue intake, external messages, scheduling, and reproduction infrastructure need real provider/runtime integrations. |
| Native agent definitions | No drop-in equivalent | Agent registration and types vary by harness. Their roles can be expressed through supported facilities, without promising native compatibility. |

## Updating while retaining local decisions

Invoke `pstack-update` to compare with the official upstream and apply useful compatible changes. Add `audit only` for a read-only comparison. New skills are recommendations until you authorize their creation. Back up local edits before reinstalling skill folders through an installer.

The updater uses source metadata, the public release baseline, and an installation-local review checkpoint. A reviewed-through commit is trusted only while the matching local fingerprint remains valid. Customizations trigger inspection, not replacement. The release baseline is immutable provenance; personal review state and optional local policy are generated separately and ignored by Git.

The updater is an agent procedure, not a background service. It does not create recurring monitors or send external notifications by default.

## Portability and validation

The core is plain `SKILL.md` instructions with supporting data. It assumes no mandatory editor API, model provider, subscription tier, browser implementation, or agent registration mechanism. Source URLs identify provenance, not runtime coupling.

Actual access to a browser, history, connectors, subagents, or filesystem writes depends on the host. Missing capabilities must be disclosed. Same-model review and sequential self-review do not reproduce a multi-model panel.

The collection's format, references, provenance, and public-data boundaries are checked before publication. NPX discovery and isolated project installation are validated with the skills CLI. Selected workflows and updater no-op comparison have been exercised in one desktop agent environment; all 21 workflows have not been executed on every supported harness. Fresh-install updater baselines are checked against the distributed files. A genuinely new upstream update and its installation path need separate live evidence.

## License

[MIT](LICENSE). Original pstack copyright: Lauren Tan. Portable adaptations and maintenance workflow: MatiasFrangolini. See [CREDITS.md](CREDITS.md) for the source snapshot and attribution.
