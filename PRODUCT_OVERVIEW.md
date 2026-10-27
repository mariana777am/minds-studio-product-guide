# Product overview

## Product thesis

Minds Studio turns AI from a temporary chat into a supervised team of collaborators called Minds. Its differentiator is the operating layer around them: Mail-assisted delegation, identity, durable Project context, visible Tasks, collaboration, scheduling and usage oversight.

## Main surfaces

1. **Email in Work mode** — manage and send email manually, or delegate the work inside a message to a Mind.
2. **Minds** — select and converse with AI collaborators that have recognizable roles and identities.
3. **Projects** — bind private instructions, conversations, files and Tasks to a durable workstream.
4. **Taskboard** — visualize delegated work and human-review states.
5. **Dashboard / Recaps** — monitor Minds, usage, spend, time saved and activity.
6. **Discover** — browse ideas, ask a Mind about an item or turn it into a recurring service.
7. **Settings / Abilities** — configure accounts, modes, identity, memory, skills, apps, voice and experimental features.
8. **Pods** — experimentally bring several Minds together as a team in Work mode.

## Product model

A user workspace contains connected accounts, Minds, Projects, Tasks and an operational ledger. A Mind has a profile, role, voice, abilities, memory and conversations or jobs. A Project contains private context, files, chats and Tasks.

Mail belongs to Work mode. A user can handle email manually or delegate email-related work to a Mind. Minds do not each automatically receive their own email address.

## Key design decisions

- **Mail-to-work continuity:** a message can become delegated, reviewable work without losing its source context.
- **Persistence:** Mind identity, memory and Project context survive beyond one prompt.
- **Supervision:** work moves through explicit human-review states.
- **Composability:** skills and apps let Minds specialize.
- **Parallelism:** Multi-Mind Tasks split one objective among several collaborators.
- **Teamwork:** experimental Pods bring selected Minds together around a shared objective.
- **Proactivity:** schedules and connected capabilities allow recurring work.
- **Economic visibility:** energy and spend make Mind activity governable.

## Pods access

Pods are experimental and available in Work mode. Enable them through **Settings → Experimental → Pods**. After activation, Pods appear in the main sidebar and under **More**. The setting applies only to the current device and may change while the feature remains experimental.

## Trust boundary

A credible implementation should keep Project files private by default, require explicit publishing, ask before irreversible or external actions, isolate tenants and accounts, defend tools against prompt injection and preserve a complete audit trail.
