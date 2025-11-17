# Software Development Life Cycle (SDLC)

## What is SDLC?

The **Software Development Life Cycle (SDLC)** is a standardized process
used by organizations to ensure efficient and high-quality delivery of
software products.
It provides a structured framework for **planning, creating, testing,
and deploying** applications.

------------------------------------------------------------------------

## 📘 Example Scenario

Consider an e-commerce website (*example.com*) with sections **Male**
and **Female**. The owner wants to add a new **Children** section.
Below are the SDLC stages involved:

------------------------------------------------------------------------

## 1. Planning & Requirements

``` mermaid
flowchart TD
    A[Identify Need] --> B[Research & Analysis]
    B --> C[Define Goal: Add Children Section]
    C --> D[Plan Resources & Timeline]
```

------------------------------------------------------------------------

## 2. Definition

Document all detailed requirements such as: - Age categories
- Product types
- UI modifications

------------------------------------------------------------------------

## 3. Design

### High-Level & Low-Level Designs

``` mermaid
flowchart LR
    HLD[High Level Design] --> LLD[Low Level Design]
    HLD --> SYS[System Architecture]
    LLD --> IMP[Implementation Steps]
```

------------------------------------------------------------------------

## 4. Testing

``` mermaid
flowchart TD
    A[Developed Code] --> B[QA Testing]
    B --> C{Bug Found?}
    C -->|Yes| A
    C -->|No| D[Ready for Deployment]
```

------------------------------------------------------------------------

## 5. Deployment

Deployed to production after verification.

------------------------------------------------------------------------

# 🔥 Additional Diagrams

## Agile vs Waterfall Model

``` mermaid
flowchart LR
    subgraph Waterfall
        A1[Requirement] --> B1[Design] --> C1[Development] --> D1[Testing] --> E1[Deployment]
    end

    subgraph Agile
        S1[Sprint 1] --> S2[Sprint 2] --> S3[Sprint 3]
        S1 --> A2[Plan/Design/Develop/Test]
        S2 --> B2[Plan/Design/Develop/Test]
        S3 --> C2[Plan/Design/Develop/Test]
    end
```

------------------------------------------------------------------------

## CI/CD Lifecycle Diagram

``` mermaid
flowchart LR
    A[Code Commit] --> B[CI: Build]
    B --> C[CI: Test]
    C --> D[CD: Deploy to Staging]
    D --> E[Approval/Automation]
    E --> F[Deploy to Production]
```

------------------------------------------------------------------------

## DevOps Tools Flow

``` mermaid
flowchart LR
    Dev[Developer] --> Git[Git/GitHub]
    Git --> CI[CI Server: Jenkins/GitHub Actions]
    CI --> Cont[Container Build: Docker]
    Cont --> Orch[Kubernetes Deployment]
    Orch --> Mon[Monitoring: Prometheus/Grafana]
    Mon --> Alert[Alerting: Slack / Email]
```

------------------------------------------------------------------------

# DevOps in SDLC

A **DevOps Engineer** automates: - Build
- Test
- Deployment
- Monitoring

### Automation Pipeline

``` mermaid
flowchart LR
    A[Code Commit] --> B[Build Automation]
    B --> C[Test Automation]
    C --> D[Deploy Automation]
    D --> E[Monitoring & Feedback]
```

------------------------------------------------------------------------

This document now includes SDLC explanation plus **Agile vs Waterfall**,
**CI/CD**, and **DevOps Tools** diagrams.
