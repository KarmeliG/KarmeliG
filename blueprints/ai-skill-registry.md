# AI Skill Registry Blueprint

## Goal

Build a lightweight registry for managing reusable AI capabilities across their lifecycle: ownership, versioning, dependencies, evaluation status, and deployment readiness.

## Core data model

Each skill should track fields such as:

```text
Name
Description
Owner
Version
Status
Dependencies
Last evaluation date
Evaluation score
Deployment status
Notes
```

## Example fictional record

```text
Skill: Research Summarizer
Version: 1.4
Owner: Marketing Operations
Status: Production
Evaluation score: 92%
Dependencies:
- brand-context
- market-context
- research-tool
Deployment readiness: Approved
```

## Suggested repository structure

```text
ai-skill-registry/
├── README.md
├── app.py
├── models.py
├── registry.py
├── sample_data/
│   └── skills.json
├── tests/
│   └── test_registry.py
└── docs/
    └── lifecycle.md
```

## V1 features

- Load a registry from JSON or CSV
- List all skills
- Filter by status or owner
- Show dependencies
- Flag skills that are missing evaluations
- Flag skills that are not deployment-ready
- Track version changes

## Later versions

- Simple web UI
- Airtable or database backend
- dependency graph
- evaluation-history table
- release notes
- automated readiness checks
- deployment approval workflow

## Portfolio story

Reusable AI capabilities become difficult to manage as organizations scale. This project explores a practical operating layer for answering basic governance questions such as: What exists? Who owns it? Which version is current? Has it been evaluated? What does it depend on? Is it safe to deploy?
