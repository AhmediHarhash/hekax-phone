# HEKAX Phone — Architecture Overview

HEKAX Phone is designed as a multi-world communication platform with a clear separation between voice operations, messaging, live control, and decision making. The goal is to provide predictable behavior, tenant safety, and a foundation suitable for long-term scale.

---

## Core Worlds

### Calls World

Responsible for:
- Inbound and outbound call flows
- Call transcription and summarization
- Caller intent detection
- Emergency and high-priority classification
- Industry-specific intake logic

Calls World interacts closely with the Voice AI stack and Codex decision engine.

### Messages World

Responsible for:
- Inbound and outbound messaging across supported channels
- Conversation grouping, threading, and status
- Smart Inbox prioritization based on Codex outputs
- Suggested replies and automated responses

Messages World consumes decisions from Codex and exposes conversation-level state to the UI and Cockpit.

### Live Control World

Responsible for:
- Real-time operational status
- SLA and queue monitoring
- Agent presence and capacity
- Surfacing alerts, warnings, and critical events

Live Control uses both raw events and Codex decisions to provide a consolidated operational view.

---

## Decision Layer — Codex

Codex is the central decision layer that evaluates events from Calls World and Messages World. It applies a chain of policies to determine:

- Priority
- Labels and classifications
- Recommended or required actions

Codex is aware of industry profiles, organization configuration, and historical context.

---

## Intelligence Layer

HEKAX Phone integrates with:
- Voice models for speech recognition and synthesis
- Small language models for low-latency reasoning
- External models when required

The intelligence layer is accessed via a dedicated orchestration service. Model selection is abstracted away from application code.

---

## Event Mesh

All significant events flow through a distributed event mesh built on streams and consumer groups. This provides:

- Decoupled processing
- Back-pressure handling
- Retry and dead-letter handling
- Real-time fan-out to WebSocket consumers

Events include call lifecycle changes, message events, Codex decisions, state transitions, and trial usage updates.

---

## State and Storage

Core persistent state is stored in a relational database, including:

- Organizations and tenants
- Users and roles
- Conversations and messages
- Calls and call summaries
- Decisions and audit records
- Trial and usage counters

Object storage is used for larger artifacts where appropriate.

---

## Tenancy and Isolation

Each organization is treated as an isolated tenant with:

- Separate logical data space
- Scoped authentication and authorization
- Clear event boundaries

The architecture is prepared for further hardening around regional isolation and compliance.

---

This overview is intended to give a clear, high-level view of how HEKAX Phone is structured. Detailed component and sequence diagrams can be maintained inside the HEKAX Architecture repository.
