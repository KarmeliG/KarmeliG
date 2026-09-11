# AI Proposal Automation Blueprint

## Goal

Build a clean-room, portfolio-safe proposal automation that demonstrates how structured intake data can become a reviewable client proposal using Python, APIs, AI-assisted drafting, deterministic business rules, and document generation.

This public version should use only fictional organizations, synthetic data, and independently written code.

## V1 architecture

```text
Intake form / sample JSON
          ↓
Structured data store
          ↓
Python proposal engine
  ├── validate required fields
  ├── normalize inputs
  ├── select proposal modules
  ├── calculate fictional pricing
  ├── generate draft narrative
  └── assemble document
          ↓
Human review
          ↓
DOCX / PDF
```

## Suggested V1 stack

- Python
- Airtable API or local JSON/CSV for the public demo
- `python-dotenv` for local secrets
- `requests` or an Airtable SDK
- `docxtpl` / `python-docx` for document generation
- Optional LLM API for narrative sections

## V1 scope

The first version only needs to:

1. Load one proposal record.
2. Validate the required fields.
3. Generate or assemble an executive summary, recommended approach, deliverables, and timeline.
4. Calculate a fictional project price using deterministic Python rules.
5. Populate a DOCX template.
6. Save the proposal to an `output/` folder for human review.

## Suggested repository structure

```text
ai-proposal-automation/
├── README.md
├── main.py
├── airtable_client.py
├── validator.py
├── generator.py
├── pricing.py
├── document_builder.py
├── requirements.txt
├── .env.example
├── sample_data/
│   └── proposal_input.json
├── templates/
│   └── README.md
├── output/
│   └── .gitkeep
└── tests/
    └── test_pricing.py
```

## Synthetic data model

Example fields:

```json
{
  "client_name": "Northstar Foundation",
  "industry": "Education",
  "organization_size": 220,
  "project_type": "Leadership Development",
  "goals": [
    "Strengthen manager effectiveness",
    "Improve accountability",
    "Build a leadership pipeline"
  ],
  "services": [
    "Organizational Assessment",
    "Manager Training",
    "Leadership Strategy"
  ],
  "duration_months": 12,
  "budget": 75000
}
```

## AI vs deterministic logic

### Good uses of AI

- Executive-summary drafting
- Tailoring an approved service description to a fictional client's goals
- Turning structured notes into concise deliverables
- Drafting an approach narrative

### Keep deterministic in Python

- Pricing calculations
- Session counts
- Discounts
- Required sections
- Dates
- Missing-field validation
- File naming

## Human-in-the-loop design

The system should create a **draft**, not autonomously send a proposal. Human review remains a deliberate quality gate before client delivery.

## V2 ideas

- Airtable status trigger
- Make orchestration
- approval workflow
- reusable proposal-section library
- multiple proposal types
- PDF conversion
- version history
- audit log
- client portal integration

## Portfolio story

The project should emphasize the systems-design question:

> How can a proposal workflow reduce repetitive work while keeping pricing, quality, and client-facing decisions under human control?
