# Product overview

## Product thesis

Minds Studio treats an AI agent less like a temporary chat and more like a teammate with an address, role and ongoing responsibilities. Its differentiator is the operating layer around agents: identity, routing, context, collaboration, supervision, scheduling and economics.

## Main surfaces

1. **Minds** — search, select and converse with individual agents.
2. **Projects** — bind private instructions, conversations, files and tasks to a durable workstream.
3. **Tasks** — visualize delegated work and human review states.
4. **Dashboard / Recaps** — monitor agents, usage, spend, time saved and activity.
5. **Discover** — browse work and ideas, then copy them into private execution.
6. **Settings / Abilities** — configure identity, memory, skills, apps, voice and experimental features.

## Product model

A user/workspace contains connected identities, Minds, Projects and an operational ledger. Each Mind has a versioned profile, voice/send-as identity, skills/apps, memory and conversations/jobs. Each Project contains private context, files, chats and tasks.

## Key design decisions

- **Addressability:** email makes a Mind callable from existing workflows.
- **Persistence:** identity, memory and project context survive beyond one prompt.
- **Supervision:** work moves through explicit human-review states.
- **Composability:** skills and apps let Minds specialize.
- **Parallelism:** multi-Mind tasks split one objective among several agents.
- **Proactivity:** schedules and Companion connections allow recurring work.
- **Economic visibility:** energy and spend make agent activity governable.

## Trust boundary

A credible implementation should keep project files private by default, require explicit publishing, ask before irreversible/external actions, isolate tenants and accounts, defend tools against prompt injection, and preserve a complete audit trail.
