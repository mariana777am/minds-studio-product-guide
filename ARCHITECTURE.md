# Reference architecture

This is an inferred reference for building a comparable system, not a claim about Minds Studio’s private implementation.

## Layers

Channels (web, mobile, email, voice) → identity/API gateway → conversation and task service → agent orchestrator → retrieval/memory + skills/apps + computer sandbox → durable queue/scheduler/event log → dashboard, recaps, audit and cost ledger.

## Suggested domain objects

User, Workspace, IdentityConnection, Mind, MindProfileVersion, CapabilityGrant, Budget, Project, ProjectMember, ProjectFile, ContextSnapshot, Conversation, Message, Artifact, Task, Assignment, TaskEvent, Approval, Schedule, JobRun, ToolCall, UsageEvent, MemoryRecord, MemorySource and AuditEvent.

## Critical properties

- Durable, resumable jobs rather than request-bound loops.
- Idempotency keys for email, schedules and tool calls.
- Tenant and project isolation at query and storage layers.
- Explicit tool scopes and per-action approvals.
- Encrypted secrets with short-lived delegated tokens.
- Sandboxed browser/computer execution with egress controls.
- Provenance from output to messages, files and tool calls.
- Usage metering per Mind, project, model and action.
- Human-readable stop, pause, retry and revoke controls.

## Vendor-neutral stack

Relational database, object storage, vector/search index, durable queue/workflow engine, append-only audit/event store, OAuth/OIDC plus magic links/passkeys, and realtime transport for streamed chat/progress/voice.
