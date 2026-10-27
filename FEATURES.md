# Feature guide

Each section separates visible product behavior from a recommended implementation pattern.

## Mail in Work mode, connected accounts and passwordless access

**Observed:** Work mode is described as “Mail and work, in a quiet look.” Its Email tab lets the user manage and send email manually. Email-related work can also be delegated to a Mind. Multiple accounts can be connected, and access is passwordless.

Minds do not each automatically receive an email address. Mail belongs to the Work experience; the user chooses when to handle communication manually and when to ask a Mind for help.

**Implement:** provide a conventional mail client backed by encrypted provider connections. Preserve account identity, threading and attachments. A delegation action should create a reviewable job linked to the source message and, when selected, its Project. Keep external sending under clear user control and log the resulting action.

## Dictation and voice

**Observed:** chat exposes dictation and voice interaction.

**Implement:** stream audio to speech-to-text, show an editable transcript, store recordings only with consent, and use low-latency text-to-speech. Support interruption, retry, language detection and captions.

## Mind identity

**Observed:** a Mind can be enabled or paused, favorited and assigned a character, profile, voice and circle. Energy is visible.

**Implement:** store versioned profiles; separate presentation from system policy; scope credentials per Mind; enforce pause at the scheduler and tool gateway; expose quotas through a budget ledger.

## Skills and apps

**Observed:** Abilities has Skills and Apps with search, categories, Added, Explore and Usage states, plus skill building.

**Implement:** capability manifests should declare inputs, permissions and versions. Use OAuth for apps, sandbox skills, show grants before activation and log every tool call, result and cost.

## Projects

**Observed:** Projects contain private descriptions and context, chats, files and Tasks. Project context can be used in a Mind conversation, and Tasks can be filtered by Project.

**Implement:** use tenant-scoped containers, Project access controls, versioned instructions, retrieval with source citations and Project IDs propagated to every chat, job and artifact.

## Taskboard

**Observed:** states are **To do**, **Doing**, **Needs you**, **Check it** and **Done**. Replies and Mind activity move cards; the human decides completion.

**Implement:** use an event-sourced state machine with idempotent transitions, separate Mind and human status, a complete audit log and notifications only at actionable boundaries.

## Multi-Mind Tasks

**Observed:** one objective can be assigned to several Minds; each assignment receives its own card and can include a due date and Project.

**Implement:** create a parent objective plus one child assignment per Mind, independent execution, an optional synthesis step, deduplicated shared actions and per-Mind progress, cost and failure state.

## Dashboard and recaps

**Observed:** the Dashboard shows waiting, on-job and quiet status, total Minds, time saved, energy used or left, Project activity and spend. Recaps summarize day or week activity and value.

**Implement:** normalize telemetry, calculate aggregates asynchronously, distinguish measured from estimated time, show confidence on value estimates and allow totals to be traced to source events.

## Discover

**Observed:** Discover has categories and social actions. **Ask a Mind** brings an item into a private conversation. **Get this daily** opens a recurring Task and schedule setup that can be reviewed before activation.

**Implement:** separate public feed objects from private execution, require explicit publishing, copy only selected content and represent recurring services as editable schedules with owner, inputs, destination and failure policy.

## Work and World modes

**Observed:** Work mode brings together Mail and work in a quiet interface. World mode presents Minds as companions for a broader and more social experience. The selected mode applies on the current device.

**Implement:** treat modes as policy and context scopes rather than visual themes. Each mode should define allowed data, tools, notifications, publishing defaults and retention.

## Pods

**Observed:** Pods are an experimental, device-specific feature for “Your Minds, working as a team.” They are available only in Work mode. Enable them through **Settings → Experimental → Pods**; once enabled, Pods appear in the main sidebar and under **More**.

**Implement:** model a Pod as a shared objective with selected Minds, explicit roles, shared context and individual execution records. Gate it with a feature flag and make membership, progress and synthesized output visible.

## Minds Computer and other experiments

**Observed:** other experimental options include Videos, fast answers, Minds Computer, automatic email, Companion, while-you-wait suggestions, memory, conversation mode, vibe matching and visual effects. Their scope varies between account-wide and device-only settings.

**Implement:** isolate computer sessions, show action previews and approvals, rate-limit autonomous loops, preserve replayable traces and provide prominent stop controls.

## Scheduled agent work

**Observed:** recurring work can be created from surfaces such as **Get this daily**, with a Task, responsible Mind and schedule reviewed before activation.

**Implement:** use a durable scheduler and queue, store timezone, make jobs idempotent, implement retry and backoff, notify only on failure, required input or meaningful completion, and allow pause, edit and run-now.

## Memory

**Observed:** users can inspect, correct and download what Minds know about them.

**Implement:** separate conversation context, Project knowledge and user memory; attach provenance and timestamps; allow source-level deletion; rebuild indexes after correction.
