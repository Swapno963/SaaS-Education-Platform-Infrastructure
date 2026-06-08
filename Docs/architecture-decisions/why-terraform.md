# ADR-005: Use Terraform for Infrastructure Provisioning

## Status

Accepted

## Context

The platform requires:

- Reproducible environments
- Infrastructure versioning
- Multi-environment deployments
- Change auditing

Manual infrastructure creation introduces drift and operational risk.

## Decision

Use Terraform as the Infrastructure as Code solution.

## Alternatives Considered

### AWS Console

Pros:
- Fast initial setup

Cons:
- Manual processes
- Configuration drift
- Difficult auditing

### AWS CloudFormation

Pros:
- Native AWS integration

Cons:
- AWS-specific
- Less portable

## Consequences

### Positive

- Infrastructure version control
- Reproducible deployments
- Environment consistency
- Easier disaster recovery

### Negative

- Learning curve
- State management complexity

## Review Date

Review if multi-cloud requirements change significantly.