# ADR-004: Use GitHub Actions for CI/CD

## Status

Accepted

## Context

The engineering team requires:

- Automated testing
- Automated container builds
- Automated deployments
- Pull request validation

Source code is hosted in GitHub.

## Decision

Use GitHub Actions as the primary CI/CD platform.

## Alternatives Considered

### Jenkins

Pros:
- Highly customizable

Cons:
- Infrastructure management required
- Maintenance overhead

### GitLab CI

Pros:
- Mature CI/CD platform

Cons:
- Additional platform management
- Source code currently hosted in GitHub

## Consequences

### Positive

- Native GitHub integration
- Minimal infrastructure management
- Fast onboarding
- Marketplace ecosystem

### Negative

- GitHub dependency
- Workflow complexity can grow over time

## Review Date

Review if pipeline requirements exceed GitHub Actions capabilities.