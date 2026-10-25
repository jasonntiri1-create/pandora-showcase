# Public Showcase Roadmap

This roadmap is for the public showcase, not a declaration that the private system's whole backlog or internal release plan is represented here.

## Phase 1 — Safe public narrative
- [x] Separate public documentation from the private source-of-truth repository.
- [x] Describe the high-level architecture without publishing runtime state or environment files.
- [x] State the limits of reported test and qualification evidence.
- [ ] Review the showcase text and diagrams for information that should remain private.

## Phase 2 — Reproducible demonstration
- [ ] Select one bounded capability that is safe to demonstrate publicly.
- [ ] Build a sanitized demo harness that does not require private keys, personal profiles, or a live device.
- [ ] Include setup instructions and fixed sample data.
- [ ] Add automated tests and a CI workflow for the public subset.
- [ ] Record a short demo video with a clear statement of the environment and limitations.

## Phase 3 — Selective source release
- [ ] Identify a self-contained component with clear licensing and low operational risk.
- [ ] Run secret scanning, dependency checks, and static analysis.
- [ ] Review the full Git history for credentials, private data, machine paths, and deployment details.
- [ ] Obtain a second review before releasing source.
- [ ] Add a license only after deciding the rights and reuse terms.

## Non-goals for this showcase
- Publishing the private repository's current contents wholesale.
- Publishing identity profiles, biometric-enrollment flags, user memory, audit logs, environment files, keys, or machine-specific configuration.
- Claiming general autonomy or universal production readiness.
