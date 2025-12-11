# HEKAX Phone — Roadmap

This roadmap outlines the planned evolution of HEKAX Phone as an enterprise communication platform. It is focused on stability, clarity, and incremental delivery of capabilities across calls, messaging, and automation.

---

## Current Focus

- Consolidate core telephony flows (sandbox, BYO, managed)
- Stabilize Calls World and Messages World interactions
- Strengthen Codex decision coverage across initial verticals
- Improve observability of events and decisions

---

## Near Term (Foundation)

### 1. Stability and Reliability

- Harden call flows for different carriers and edge cases
- Improve retry, timeout, and error handling across all channels
- Strengthen logging and tracing for calls, messages, and Codex decisions

### 2. Smart Inbox Enhancements

- Refine prioritization logic using Codex outputs
- Improve conversation grouping, assignment, and filtering
- Align Inbox views with Exec Cockpit metrics

### 3. Trial Experience

- Finalize the guided "first call" and "first message" path
- Clarify trial limits and upgrade paths inside the UI
- Improve empty states and usage feedback

---

## Mid Term (Intelligence and Verticalization)

### 1. Vertical Profiles

- Expand industry-specific configurations for law, medical, home services, SaaS, and BPO
- Align Cockpit views with vertical KPIs (e.g., urgent cases, emergency calls, high-value leads)
- Extend Codex policies for vertical-specific labels and actions

### 2. Automation Layer

- Introduce reusable automation patterns (follow-up, reminders, routing)
- Add event-based triggers and conditions based on Codex decisions
- Integrate state machine workflows for leads and conversations

### 3. Exec Cockpit

- Add profile-aware dashboards with clear metrics for owners and managers
- Provide visibility into SLA, queue health, and decision quality
- Surface high-value and high-risk signals from Codex

---

## Longer Term (Scale and Ecosystem)

### 1. Multi-Org and Multi-Region

- Support organizations across regions with tenant-safe isolation
- Prepare for data residency and compliance requirements

### 2. Partner and Integration Surface

- Expose stable APIs and webhooks for third-party integrations
- Provide clear patterns for connecting external CRMs and tools

### 3. Advanced Intelligence

- Refine model routing strategies between SLMs and external LLMs
- Improve explainability for Codex decisions
- Support more complex routing, escalation, and multi-step workflows

---

This roadmap is intentionally high-level. The priority is to maintain a clear, predictable platform that can be incrementally expanded without sacrificing reliability.
