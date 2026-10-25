# Pandora Architecture

This document summarizes the system boundaries at a public, high level. It is not a substitute for the private implementation or a complete security design.

## Design objective

Pandora aims to preserve working context over time and connect it to task execution. The intent is to move beyond a stateless conversational surface while retaining clear boundaries between understanding a request, deciding what should happen, performing an action, and recording the result.

## Conceptual components

### 1. Context and world model

Represents selected goals, project context, ongoing work, and observations so the system can resume work without relying solely on the most recent prompt.

### 2. Task orchestration

Coordinates tasks and makes lifecycle state explicit. Important states such as pending approval, queued, running, completed, cancelled, or failed should not be interchangeable. Transitions must be checked so a generic state update cannot bypass an approval boundary.

### 3. Model and capability routing

Connects requests to available AI model capabilities. The design goal is to route work to appropriate capabilities while allowing configured providers to differ between environments.

### 4. Governance and approvals

Places a policy boundary between a planned action and its execution. The system design distinguishes ordinary read/assist work from actions that could affect devices, finances, security, or other consequential resources. Depending on policy and risk, an action may be allowed, require approval, or be denied.

### 5. Tools and integrations

Provides the interface to selected tools and integrations. Integrations are treated as capability boundaries: the ability to formulate a request does not automatically mean the action should be executed.

### 6. Observability and recovery

Tracks task and service health, reports errors, and supports recovery paths where implemented. Monitoring should expose useful system state without making private logs or runtime memory part of the public showcase.

## Data and control flow

1. A user expresses an intent.
2. Relevant context is retrieved or updated.
3. The task layer forms and manages the work.
4. A model or capability provider assists with reasoning or transformation.
5. Tool-bound actions pass through the applicable policy and approval controls.
6. The system records the result and updates the task/context state.
7. Monitoring and recovery mechanisms observe runtime health.

This sequence describes the intended high-level pattern; not every task follows every step, and the exact runtime behavior depends on configuration and subsystem readiness.

## Architecture principles

- **Explicit state:** represent task lifecycle and persisted context deliberately.
- **Single ownership:** avoid parallel, competing sources of truth for task status or orchestration.
- **Policy before execution:** check consequential actions at the execution boundary.
- **Fail closed where practical:** missing or uncertain policy should not silently grant authority for a high-impact action.
- **Observable behavior:** tests and health signals should substantiate reliability claims.
- **Modular providers:** external model and tool integrations should be replaceable without duplicating the core runtime.

## Deliberate omissions

This public document does not expose detailed internal endpoints, key storage formats, device protocol internals, operational scripts, local paths, live configuration, or implementation details for sensitive subsystems. Those remain in the private source of truth and require a separate review before any selective release.
