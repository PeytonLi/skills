---
name: review-architecture
description: "Use when you need a complete top-down architecture audit of any codebase, including full exploration of major paths, endpoint mapping, current-vs-target user journeys from documentation, and deep issue remediation plans with step-by-step fixes. Trigger phrases: architecture audit, full codebase walkthrough, map all endpoints, user journey analysis, current vs desired product flow, find and fix project issues, end-to-end architecture review."
---

# Project Architecture Deep Audit Skill

## Purpose
Produce a complete, evidence-based architecture report for any repository with:
1. Full top-down architecture mapping.
2. Exploration of all major runtime paths (UI routes, API routes, background jobs, integration boundaries, data paths).
3. API endpoint behavior matrix.
4. Current user journey vs target user journey from product docs.
5. Deep issue analysis with concrete, step-by-step fixes.

This skill is designed for portability and must not return a shallow overview.

## Scope
You must analyze all of the following layers in order:
1. Product intent and target behavior from project docs.
2. Runtime architecture and dependencies.
3. Frontend user-facing routes and UI states.
4. API boundary layer (BFF/gateway/services) and auth/rate-limiting behavior.
5. Backend endpoints and business-domain dependencies.
6. Data layer (storage models, cache strategy, consistency boundaries).
7. Background processing, pipelines, workers, schedulers, and model/inference paths (if present).
8. End-to-end journey continuity and failure points.

## Required Inputs
You must read enough files to establish evidence for every major path before making conclusions.

At minimum, discover and inspect files in these categories if they exist.

### Product intent and setup
- Root docs: README*, CONTRIBUTING*, docs/*, architecture docs, product specs
- Runtime setup: compose/manifests, lockfiles, package manifests, env templates

### User experience layer
- Entry pages/routes and their linked flows
- Shared layout/navigation components that affect user journey branching
- Error/loading/empty states for critical pages

### API boundary layer
- Gateway/BFF handlers, controllers, route declarations, middleware
- Request/response schemas and validation modules

### Backend and core domain
- App entrypoints, routers/controllers, service/domain modules
- Auth, permission, feature flag, or usage controls

### Data and async processing
- Database models/migrations/repositories
- Jobs, workers, schedulers, pipelines, integration clients
- ML training/inference/explainability modules (when applicable)

If a category is expected but absent, explicitly note it as a finding.

## Discovery Procedure (Portable)
Use this sequence to adapt to any stack.

1. Detect major technologies and frameworks from manifests and entrypoints.
2. Locate route declarations and endpoint registration points.
3. Locate user entry routes and primary conversion flows.
4. Locate domain services, data access boundaries, and async jobs.
5. Build a dependency map from user action -> API -> domain -> data -> side effects.
6. Verify assumptions with code evidence before writing findings.

## Non-Negotiable Workflow
Follow this exact workflow every time.

### Phase 1: Build top-down system map
1. Extract promised behavior from product/docs.
2. Map actual implemented modules by layer:
- Entry points
- User entry routes
- API boundary
- Data/ML internals
3. Create a "promised vs implemented" baseline before issue analysis.

### Phase 2: Enumerate all endpoints and paths
For each endpoint, document method, input contract, output contract, dependencies, and error paths.

You must include:
- Public user-facing routes
- Public/internal API endpoints
- Webhook/callback endpoints (if present)
- Health/readiness endpoints (if present)

For each endpoint, capture:
1. Who calls it.
2. Required preconditions.
3. Fallback/error behavior.
4. UX consequence if it fails.

### Phase 3: User journey deep dive
Construct end-to-end journeys from user perspective.

Required journeys:
1. Primary happy path from first entry to core value delivered.
2. Billing/quota/permission denial path (if product has gating).
3. Invalid input path for core action.
4. Dependency outage path (backend/db/external API/model unavailable).
5. Secondary/non-core navigation paths and their continuity.

For each journey, provide:
1. Steps in order.
2. API calls made at each step.
3. Possible breakpoints.
4. Current observed UX behavior.

### Phase 4: Current vs target journey comparison
Use product docs/README as source of truth for desired product behavior.

Create a side-by-side analysis:
1. Current behavior (what code does now).
2. Target behavior (what README promises/vision implies).
3. Gap.
4. Severity (Critical, High, Medium, Low).
5. Why this gap matters to real users/business goals.

### Phase 5: Issue discovery and root-cause analysis
Analyze technical and product issues including:
- Broken route wiring
- Contract mismatches between frontend and backend
- Placeholder pages blocking key user value
- Non-persistent state limitations (cache/session/quota)
- Billing/checkout integration gaps (if applicable)
- Missing observability and resilience behavior
- Data pipeline/model readiness risk (if applicable)
- Security/configuration risks

Every issue must include:
1. Evidence with exact file references.
2. Root cause.
3. User impact.
4. Engineering impact.
5. Reproduction path.

### Phase 6: In-depth fix plans
For each issue, provide a detailed remediation plan:
1. Immediate fix (minimal viable correction).
2. Robust fix (production-grade).
3. Exact files to modify.
4. Suggested implementation sequence.
5. Validation plan (manual + automated tests).
6. Rollout risk and rollback strategy.

## Required Output Format
Return output in this order.

### 1) Executive architecture summary
- One concise top-down summary of the full system as implemented now.

### 2) Full architecture map
- Layer-by-layer breakdown from UI down to DB/ML artifacts.
- Include data flow from player tag input to recommendation output.

### 3) Endpoint contract matrix
For every endpoint list:
- Path + method
- Caller
- Dependencies
- Success response shape
- Error cases
- Notes on mismatches or fragility

### 4) User journey matrix
For each required journey include:
- Step-by-step flow
- API touches
- UX states
- Failure states

### 5) Current vs desired experience
A table with columns:
- Capability
- Current behavior
- Desired behavior (docs/README)
- Gap
- Severity

### 6) Issues and deep fixes
For each issue:
- Issue title
- Severity
- Evidence
- Root cause
- User impact
- Step-by-step fix plan
- Test plan

### 7) Prioritized implementation roadmap
- Top-down sequence for fixes:
1. Stabilize core flow
2. Close product-vision gaps
3. Production hardening

Each item must include:
- Objective
- Files
- Dependencies
- Definition of done

## Quality Bar
Do not pass if any of these are true:
- You skipped major paths in the discovered architecture.
- You described architecture without endpoint contracts.
- You gave generic "improve X" advice without concrete file-level fixes.
- You did not compare current behavior to documented product promises.
- You did not describe user-visible failure modes.

## Ground Rules
1. Evidence only: do not invent behavior not supported by code/docs.
2. Be explicit about uncertainty: "not found in code" when applicable.
3. Prefer deterministic findings over assumptions.
4. Keep recommendations implementation-ready.
5. If the repository is large, prioritize core production paths first, then expand to supporting paths.
6. If multiple services/repos are present, audit each service and then produce a cross-service integration map.

## Optional Advanced Pass (if requested)
Include:
1. Sequence diagrams for core journeys.
2. A test coverage matrix by journey and endpoint.
3. A migration plan from ephemeral state to persistent/reliable infrastructure where needed.
4. A deployment-readiness checklist for the detected hosting/runtime topology.

## Publishing Notes
For public distribution:
1. Keep this skill free of repository-specific file paths.
2. Keep trigger phrases broad and architecture-focused.
3. Require evidence-linked findings to reduce hallucinated analysis.
4. Keep output schema stable so downstream users can automate review consumption.
