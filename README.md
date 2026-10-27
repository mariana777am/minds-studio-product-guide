# Minds Studio — Product Guide

An independent, screenshot-backed guide to **Minds Studio**, a workspace that brings together email, AI collaborators (“Minds”), Projects, Tasks and recurring work. Written for both humans and AI crawlers.

> Observed on 26–27 October 2026 at https://minds.email. This is not official documentation and is not affiliated with Minds Studio or Animoca Brands. Product behavior may change.

## The product in one sentence

Minds Studio lets users manage email in Work mode, delegate email-related work or other objectives to specialized Minds, organize durable context in Projects, supervise progress on a Taskboard and run useful recurring work with visible human review.

## Start with the product introduction

Read **[Meet Minds Studio: Build an AI Team That Actually Gets Work Done](PRODUCT_INTRODUCTION.md)** for a friendly, non-technical introduction with screenshots and a first-day workflow.

## What matters most

| Capability | Purpose |
|---|---|
| Mail in Work mode | Read and send email manually, or delegate the work inside a message to a Mind |
| Multiple accounts | Operate across personal and work identities |
| Passwordless access | Reduce onboarding and credential friction |
| Dictation and voice | Delegate naturally and accessibly |
| Mind identity | Give AI collaborators recognizable roles, profiles and voices |
| Projects | Hold private context, conversations, files and Tasks |
| Taskboard | Track To do → Doing → Needs you → Check it → Done |
| Multi-Mind Tasks | Give one objective to several specialists with separate cards |
| Dashboard and recaps | Show status, time saved, energy, activity and spend |
| Discover | Turn shared ideas into private chats or recurring services |
| Work / World modes | Separate focused work from broader exploration |
| Pods | Bring several Minds together as a team in Work mode |
| Scheduled work | Run visible recurring services |
| Skills, apps and memory | Specialize Minds and retain governed context |

## Core operating loop

Connect an account → choose or configure a Mind → add Project context → delegate by chat, email, dictation or voice → track progress on the Taskboard → provide input or approve results → reuse or schedule the workflow.

## Documentation

- [Social product introduction](PRODUCT_INTRODUCTION.md)
- [Product overview](PRODUCT_OVERVIEW.md)
- [Feature guide](FEATURES.md)
- [User flows](USER_FLOWS.md)
- [Reference architecture](ARCHITECTURE.md)
- [Implementation roadmap](IMPLEMENTATION_ROADMAP.md)
- [Presentation outline](PRESENTATION_OUTLINE.md)
- [Machine-readable feature catalog](feature-catalog.json)
- [AI crawler summary](llms.txt) and [full AI context](llms-full.txt)
- [Screenshot gallery](assets/screenshots/)

## Screenshot tour

See the [screenshot gallery](assets/screenshots/) for Minds, connected accounts and modes, Pods, Dashboard, Taskboard, Multi-Mind Tasks, Projects, Discover, Mind identity, abilities and voice.

## Reading this repository correctly

- **Observed** means visible in the inspected product UI.
- **Inferred** means a reasonable implementation pattern, not a claim about private code.
- **Recommended** means guidance for building a comparable system.
- Experimental features should not be assumed production-stable.
- Minds do not each automatically receive an email address; Mail is part of Work mode and email-related work can be delegated to a Mind.
