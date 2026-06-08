# ADR-003: Use OpenTelemetry for Observability

## Status

Accepted

## Context

The application consists of multiple components:

* Browser
* Next.js Frontend
* Go Backend API
* PostgreSQL Database

Traditional logs alone make troubleshooting distributed requests difficult.

The team requires end-to-end visibility into request execution.

## Decision

Adopt OpenTelemetry as the standard instrumentation framework.

## Alternatives Considered

### Logging Only

Pros:

* Easy implementation

Cons:

* Difficult root-cause analysis
* Limited request visibility

### Vendor-Specific Instrumentation

Pros:

* Deep vendor integration

Cons:

* Vendor lock-in
* Reduced portability

## Consequences

### Positive

* Distributed tracing
* Vendor-neutral standard
* Performance bottleneck identification
* Faster incident resolution

### Negative

* Additional infrastructure
* Slight application overhead
* Increased observability complexity

## Review Date

Review if tracing costs exceed operational benefits.
