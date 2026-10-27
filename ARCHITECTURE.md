# Reference architecture

This is an inferred reference for building a comparable system, not a claim about Minds Studio’s private implementation.

## Layers

Channels (web, mobile, Work-mode Mail, dictation and voice) → identity/API gateway → conversation and Task service → Mind orchestrator → retrieval/memory + skills/apps + computer sandbox → durable queue/scheduler/event log → Dashboard, recaps, audit and cost ledger.

## Suggested domain objects

User, Workspace, IdentityConnection, MailAccount, EmailThread, EmailMessage, DelegationSource, Mind, MindProfileVersion, CapabilityGrant, Budget, Project, ProjectMember, ProjectFile, ContextSnapshot, Conversation, Message, Artifact, Task, Assignment, TaskEvent, Approval, Schedule, JobRun, ToolCall, UsageEvent, MemoryRecord, MemorySource, Pod and AuditEvent.

## Mail-to-work model

Mail belongs to the user’s Work-mode experience; it should not be modeled as an automatic inbox per Mind. The user may send email manually or create a delegated job from an EmailMessage. Preserve the source thread, selected attachments, account identity and Project association. Keep draft review and external sending as distinct, auditable actions.

## Critical properties

- Durable, resumable jobs rather than request-bound loops.
- Idempotency keys for email actions, schedules and tool calls.
- Tenant, account and Project isolation at query and storage layers.
- Explicit tool scopes and per-action approvals.
- Encrypted secrets with short-lived delegated tokens.
- Sandboxed browser and computer execution with egress controls.
- Provenance from output to email, messages, files and tool calls.
- Usage metering per Mind, Project, model and action.
- Human-readable stop, pause, retry and revoke controls.
- Separate records for a shared Pod objective and each Mind’s contribution.

## Vendor-neutral stack

Relational database, object storage, vector or search index, durable queue or workflow engine, append-only audit/event store, OAuth/OIDC plus magic links or passkeys, and realtime transport for streamed chat, progress and voice.
