---
name: pstack-ketchup
description: "Catch the user up on progress in the current chat since their previous message, including outcomes, remaining work, and every pending decision with enough context to act. Use for pstack-ketchup or a current-chat progress catch-up."
license: MIT
metadata:
  upstream: https://github.com/cursor/plugins/tree/88d47514b82e7c44f00f2b2a72ff6dd12158038c/pstack/skills/ketchup
  upstream-commit: 88d47514b82e7c44f00f2b2a72ff6dd12158038c
  adaptation: portable-chat-inherited
---

# Ketchup

Give a short current-state catch-up. This skill covers progress in this chat; reconstructing a topic across chats is a separate recall task.

## Environment contract

Use the active chat model and its current reasoning settings. Delegate only when supported and authorized; omit model and effort overrides when omission inherits the chat settings. If the host cannot guarantee that inheritance, do the work in the current chat. Sequential passes are a fallback, not independent reviewers.

Use available file, search, terminal, browser, history, and connector tools. Follow the user's scope, authorization, repository instructions, and local resource controls. A skill invocation does not authorize publication, unrelated changes, or external messages.

## Gather the changes

Use the last human message before the catch-up request as the starting point, unless the user names another interval. Agent reports and notifications do not reset that point. Include earlier decisions still waiting on the user. If that history is unavailable, state the boundary of the available record.

Keep the catch-up read-only: use existing work and artifacts, without starting an app, build, test, or new implementation. It does not cancel or broaden ongoing work. Refresh only relevant artifact, PR, CI, or agent state through available read-only tools. Otherwise label the state historical or unverified.

Distinguish source inspection, local checks, CI results, and deployed/provider behavior. A worker report or green build is not proof of the user flow. Check numbers against their evidence and acknowledge corrections. Retain an exact version or head when it affects the user's decision.

## Explain what matters

Lead with what changed and whether anything needs the user. In plain language, cover the requested outcomes, what is done or still running, failures or unchecked behavior, and work the agent can still do.

List every pending action item the user owns: a decision, approval, or missing access, including those raised before the reporting interval. For each item, give its recognizable name and available link, what it changes for users, your recommendation, the evidence behind it, and its risk. Mark necessary unknown facts explicitly. Authorized work the agent can complete is not an action item. Preserve existing approval boundaries and do not invent a decision to fill the reply.

When one decision covers several items, state the decision and recommendation once, then list each affected item with its own context, evidence, and risk, highest risk first. For competing options, give each option's gain and cost. Explain the cost of waiting only when it adds a concrete consequence beyond delay.

Keep the progress summary short, usually under 100 words. Let the reply grow with the pending decisions; never omit an item, compress the list into a count, or substitute a link for the context needed to decide. Use the user's language and recognizable names. Links add detail; the reply itself must support each decision.

## Visual evidence

Embed existing screenshots or videos when they explain a visible change. A small diagram from observed facts can explain a relationship or choice when useful. Use the host's available rendering tools; no particular provider is required. Never fabricate a screenshot, result, or number. If a visible result lacks capture, say so without starting a new verification run just for this summary.
