# Feature guide

Each section describes observed behavior and a recommended implementation pattern.

## Email, multi-account and passwordless access

**Observed:** email is both an access method and a work channel. Multiple connected accounts can be consolidated.

**Implement:** use magic links or passkeys; maintain one encrypted provider connection per identity; normalize inbound email through a routing service; map aliases to Mind IDs; thread by provider message IDs; require confirmation before external sends.

## Dictation and voice

**Observed:** chat exposes dictation and voice interaction.

**Implement:** stream audio to speech-to-text, show an editable transcript, store recordings only with consent, and use low-latency text-to-speech. Support interruption, retry, language detection and captions.

## Mind identity

**Observed:** a Mind can be enabled/paused, favorited, assigned a character/profile/voice/circle and configured for send-as behavior. Energy is visible.

**Implement:** store versioned profiles; separate presentation from system policy; scope credentials per Mind; enforce pause at scheduler/tool gateway; expose quotas through a budget ledger.

## Skills and apps

**Observed:** Abilities has Skills and Apps with search, categories, Added/Explore/Usage states and skill building.

**Implement:** capability manifests should declare inputs, permissions and versions. Use OAuth for apps, sandbox skills, show grants before activation and log every tool call, result and cost.

## Projects

**Observed:** projects contain private descriptions/context, chats and files. Context can be attached to a Mind conversation; files have privacy controls; tasks can be filtered by project.

**Implement:** tenant-scoped containers, project ACLs, versioned instructions, retrieval with source citations, and project IDs propagated to every chat, job and artifact.

## Task board

**Observed:** states are **To do**, **Doing**, **Needs you**, **Check it** and **Done**. Replies and agent activity move cards; the human decides completion.

**Implement:** an event-sourced state machine with idempotent transitions, separate agent/human status, a complete audit log and notifications only at actionable boundaries.

## Multi-Mind tasks

**Observed:** one task can be sent to several Minds; each assignment receives its own card and can include a due date, project and email dispatch.

**Implement:** a parent objective plus one child assignment per Mind; independent execution; synthesis step; deduplicated shared actions; per-agent progress, cost and failure state.

## Dashboard and recaps

**Observed:** waiting/on-job/quiet status, total Minds, time saved, energy used/left, project activity and spend by Mind/action. Recaps summarize day/week and value versus cost.

**Implement:** normalized telemetry, asynchronous aggregates, explicit measured versus estimated time, confidence on ROI, and drill-down from totals to source events.

## Discover

**Observed:** categories, like, comment, listen, share and save. “Ask a Mind” copies an item into private chat; “Get this daily” creates a recurring service.

**Implement:** separate public feed objects from private execution; explicit publish; copy only selected content; represent recurring services as editable schedules with owner, inputs, destination and failure policy.

## Work and World modes

Treat modes as policy/context scopes, not themes: each mode defines allowed data, tools, notifications, publishing defaults and retention.

## Pods, Minds Computer and experiments

Observed experiments include Pods, Videos, fast answers, Minds Computer, automatic email, Companion, while-you-wait, memory, voice conversation, vibe matching and effects.

Gate with feature flags; isolate computer sessions; show action previews/approvals; rate-limit autonomous loops; preserve replayable traces and prominent stop controls.

## Scheduled agent work

Use a durable scheduler and queue; store timezone; make jobs idempotent; implement retry/backoff and dead-letter handling; notify only on failure, required input or meaningful completion; allow pause/edit/run-now.

## Memory

Users can inspect, correct, forget and download memory. Separate conversation context, project knowledge and user memory; attach provenance/timestamps; allow source-level deletion; rebuild indexes after correction.
