# SaaS Education Platform Infrastructure

Production-ready infrastructure automation for a SaaS-based School Management System.

## Overview

This repository contains Infrastructure as Code (IaC), deployment automation, observability configuration, and operational tooling for a cloud-native education platform.

### Application Stack

* Backend: Go
* Frontend: Next.js
* Database: PostgreSQL
* Containerization: Docker
* Infrastructure: Terraform
* Cloud Provider: AWS
* Orchestration: Kubernetes (EKS)
* CI/CD: GitHub Actions
* Monitoring: Prometheus + Grafana
* Logging: Loki
* Tracing: OpenTelemetry
* Secrets Management: AWS Secrets Manager

---

## Architecture

```text
Users
  │
  ▼
Route53
  │
  ▼
Application Load Balancer
  │
  ▼
Kubernetes (EKS)
 ├── Frontend (Next.js)
 ├── Backend API (Go)
 └── Background Workers
  │
  ▼
PostgreSQL (RDS)
```

---

## Repository Structure

```text
infra/
├── terraform/
│   ├── modules/
│   │   ├── vpc/
│   │   ├── eks/
│   │   ├── rds/
│   │   ├── alb/
│   │   └── monitoring/
│   │
│   └── environments/
│       ├── dev/
│       ├── staging/
│       └── prod/
│
├── kubernetes/
│   ├── backend/
│   ├── frontend/
│   ├── ingress/
│   ├── monitoring/
│   └── logging/
│
├── github-actions/
│
├── scripts/
│
└── docs/
```

---

# Infrastructure Components

## Networking

* Custom VPC
* Public and Private Subnets
* Internet Gateway
* NAT Gateway
* Route Tables
* Security Groups

### Goals

* Isolated workloads
* Secure database access
* Production-ready network segmentation

---

## Kubernetes Cluster

### Features

* Managed EKS Cluster
* Node Groups
* Horizontal Pod Autoscaling
* Rolling Updates
* Health Checks
* Resource Limits

### Workloads

| Service  | Description         |
| -------- | ------------------- |
| frontend | Next.js Application |
| api      | Go REST API         |
| worker   | Background Jobs     |

---

## Database

### PostgreSQL (RDS)

Features:

* Automated Backups
* Point-In-Time Recovery
* Multi-AZ Deployment
* Monitoring Enabled

---

## CI/CD Pipeline

### Deployment Flow

```text
Developer Push
        │
        ▼
GitHub Actions
        │
        ├── Run Tests
        ├── Lint
        ├── Build Docker Image
        ├── Security Scan
        ├── Push To Registry
        └── Deploy To Kubernetes
```

### Objectives

* Automated Deployments
* Consistent Releases
* Fast Rollbacks

---

## Monitoring

### Prometheus

Collected Metrics:

* CPU Usage
* Memory Usage
* Pod Health
* Request Count
* Request Latency
* Error Rate

### Grafana Dashboards

#### Application Dashboard

* Requests Per Second
* P95 Latency
* Error Percentage
* Active Users

#### Infrastructure Dashboard

* Node Health
* CPU
* Memory
* Storage

---

## Logging

### Centralized Logging

Components:

* Loki
* Promtail

Log Types:

* Application Logs
* Audit Logs
* Access Logs
* Error Logs

---

## Distributed Tracing

### OpenTelemetry

Trace Flow:

```text
Browser
  │
  ▼
Frontend
  │
  ▼
Backend API
  │
  ▼
PostgreSQL
```

Benefits:

* Root Cause Analysis
* Performance Investigation
* Request Lifecycle Visibility

---

## Security

### Secrets Management

Managed using:

* AWS Secrets Manager

Examples:

* Database Credentials
* API Keys
* JWT Secrets

### Container Security

* Non-root containers
* Image vulnerability scanning
* Minimal base images

### IAM

* Least Privilege Access
* Role-Based Permissions
* Environment Isolation

---

## Disaster Recovery

### Backup Strategy

Database:

* Daily Backups
* Point-In-Time Recovery

Storage:

* Versioned S3 Buckets

### Recovery Objectives

| Metric | Target     |
| ------ | ---------- |
| RPO    | 15 Minutes |
| RTO    | 1 Hour     |

---

## Environments

### Development

Purpose:

* Feature Development
* Local Testing

### Staging

Purpose:

* Pre-production Validation
* Performance Testing

### Production

Purpose:

* Customer Workloads
* High Availability

---

## Operational Responsibilities

This infrastructure supports:

* Automated provisioning
* Automated deployments
* Monitoring and alerting
* Capacity planning
* Incident response
* Backup verification
* Security compliance

---

## Future Improvements

* GitOps using ArgoCD
* Service Mesh
* Multi-Region Disaster Recovery
* Cost Optimization Dashboards
* Automated Chaos Testing

---

## Skills Demonstrated

* Go Application Operations
* AWS Cloud Infrastructure
* Terraform
* Docker
* Kubernetes
* PostgreSQL Administration
* CI/CD Engineering
* Monitoring and Alerting
* Distributed Tracing
* Infrastructure Automation
* Site Reliability Practices
* Production Operations
* Incident Management
* Cloud Security
