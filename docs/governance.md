# Governance and Safety Principles

Pandora is intended to interact with tools and potentially consequential resources. That makes clear authority boundaries a core engineering concern, not a final layer of polish.

This document summarizes the principles the project is designed to support. It is not a certification, a guarantee of safety, or a substitute for evaluating each implementation path.

## Principles

### Separate intent from authority

A user's goal, a model's plan, and permission to execute an operation are different things. The system should not infer blanket authority merely because an action appears useful or follows naturally from a conversation.

### Classify consequential operations

Actions that can affect devices, finances, security, or other high-impact resources deserve stricter treatment than ordinary information retrieval or drafting. Risk classification should be explicit and should not depend only on natural-language model judgment.

### Use approval boundaries

Where an action requires human approval, the approval state must be represented in the task lifecycle. Generic task updates must not bypass the intended confirmation/approval path. Cancellation should be terminal for the cancelled task and must not be silently undone by a later transition.

### Fail safely under uncertainty

Missing policy, unavailable authorization state, or ambiguous identity should not quietly increase the system's permissions. Uncertainty should lead to a defined safe response—such as asking for clarification, requiring confirmation, or refusing the operation—according to the action's risk.

### Maintain accountability

Task outcomes, policy decisions, and relevant execution events should be inspectable for debugging and accountability. Audit data itself can contain private information, so logging and retention require data-minimization and access controls.

### Protect identity and runtime state

User profiles, authentication material, credentials, local memory, device inventories, and runtime snapshots are private operational data. They are excluded from this public showcase.

## Review questions for every integration

- What permissions does the integration need?
- Which actions can change external state?
- Which actions require an explicit confirmation?
- What happens when policy or identity cannot be resolved?
- Can a task be cancelled or retried without duplicating side effects?
- Are secrets and private context excluded from logs and source control?
- Can the action's result be verified independently?

## Scope and limits

These are design principles and selected engineering goals. They do not mean every subsystem has undergone an independent security audit. The private implementation contains additional code and integrations that are intentionally not reproduced here.
