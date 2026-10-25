# Engineering Evidence and Limitations

This page records selected evidence described in the private Pandora project documentation. It is intentionally conservative: reported results are attributed to their documented checkpoint and are not represented as independent verification by this public repository.

## Test-suite checkpoint

The private project's README records a September 2026 test-suite result after task-lifecycle and queue-pause/resume work:

| Metric | Documented result |
| --- | ---: |
| Passed | 747 |
| Skipped | 101 |
| Failed | 0 |

**Important:** this was a result recorded in the private project's documentation. The suite has not been rerun in this public showcase, and no test runner or implementation is included here. A future public demonstration should carry its own reproducible tests and CI results.

## Cross-platform startup qualification

Project documentation reports that a Windows login/autostart qualification on September 16, 2026 completed all 23 startup stages, with the service reporting healthy status after startup. The documentation also describes runtime qualification on Linux.

These are records from the development environment, not a guarantee of identical behavior on other machines. The raw operational reports, machine-specific paths, and logs are deliberately excluded from this repository.

## Engineering areas represented in the private project

The source-of-truth repository contains work spanning:

- Persistent context and world-model state
- Task lifecycle and orchestration
- Model-provider and capability routing
- Approval-gated actions and policy enforcement
- Service health, runtime supervision, and recovery
- Integrations and cross-platform behavior
- Unit, integration, and qualification tests

The existence of a module does not prove it is production-ready. The maturity of each capability varies and should be demonstrated separately.

## What would make the evidence stronger

A responsible public release should add:

1. A reproducible demonstration with documented prerequisites.
2. Automated tests that run against the public subset.
3. Continuous integration with visible pass/fail results.
4. An explicit list of what the demonstration does and does not prove.
5. A release review covering secrets, personal data, dependencies, licensing, and historical artifacts.

## Reporting standard

When describing Pandora publicly, distinguish among:
- **Implemented:** the code path exists.
- **Tested:** a specific test or qualification was run at a stated point in time.
- **Demonstrated:** a reviewer can reproduce a visible behavior using documented steps.
- **Planned:** a future capability or desired outcome.

This distinction is essential to avoid overstating the system's readiness.
