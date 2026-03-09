<p align="center">
  <img src="https://raw.githubusercontent.com/ForgePrime/.github/main/assets/forge-banner.png" alt="ForgePrime" width="720"/>
</p>

<p align="center">
  <strong>Structured AI Development with Full Traceability</strong><br/>
  Every code change — planned, tracked, reasoned about, and auditable.
</p>

<p align="center">
  <a href="https://github.com/ForgePrime/forge"><img src="https://img.shields.io/badge/forge-core_engine-2D3748?style=for-the-badge&logo=github" alt="Forge Core"/></a>&nbsp;
  <a href="https://github.com/ForgePrime/forge/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-C8956C?style=for-the-badge" alt="License"/></a>&nbsp;
  <a href="https://github.com/ForgePrime/forge/stargazers"><img src="https://img.shields.io/github/stars/ForgePrime/forge?style=for-the-badge&color=2D3748" alt="Stars"/></a>
</p>

---

## The Problem

AI coding assistants generate code fast — but without structure. There is no audit trail, no decision history, no way to answer **"why was this done?"** six months later. Teams lose visibility, reviewers lose context, and technical debt compounds silently.

## Our Solution

**Forge** is a structured change orchestrator for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). It wraps AI-driven development in a rigorous, traceable process:

```
Idea  →  Discover  →  Plan  →  Guide  →  Execute  →  Validate  →  Learn
```

Every step produces auditable artifacts — decisions with provenance, changes with reasoning traces, project guidelines that keep AI aligned with your standards, and validation gates that enforce quality before completion.

---

## Repositories

| | Repository | Description | Status |
|:-:|:-----------|:------------|:------:|
| <a href="https://github.com/ForgePrime/forge"><img src="https://raw.githubusercontent.com/ForgePrime/forge/main/img/ico.png" alt="Forge" width="28"/></a> | [**forge**](https://github.com/ForgePrime/forge) | Core orchestrator — pipeline, decisions, changes, gates, learning | Active |

---

## What Forge Delivers

<table>
<tr>
<td width="50%" valign="top">

### For Engineering Teams

- **Decision Log** — every architectural choice recorded with alternatives, reasoning, and who decided (human vs AI)
- **Change Traceability** — every file modification linked to a task, decision, and reasoning trace
- **Project Guidelines** — scoped coding standards and conventions automatically injected into every task context
- **Validation Gates** — tests, lint, and secret scanning run automatically before task completion
- **Compound Learning** — lessons from past projects inform future ones across your organization

</td>
<td width="50%" valign="top">

### For Engineering Leaders

- **Full Audit Trail** — answer "why was this built this way?" at any time
- **Risk Visibility** — 5-dimensional risk assessment with severity, likelihood, and mitigation tracking
- **Resumability** — interrupt and resume at any point; state persists in structured JSON
- **Multi-Agent Support** — parallel AI agents with dependency awareness and conflict detection

</td>
</tr>
</table>

---

## How It Works

```
                     ┌──────────────────────────────────────┐
                     │            USER INTENT                │
                     │       "Add JWT auth to API"           │
                     └───────────────┬──────────────────────┘
                                     │
                     ┌───────────────▼──────────────────────┐
                     │   /idea  →  /discover  →  /plan      │
                     │   Stage ideas, explore options,       │
                     │   assess risks, build task graph      │
                     └───────────────┬──────────────────────┘
                                     │
                     ┌───────────────▼──────────────────────┐
                     │   /guideline  →  Set standards        │
                     │   "Use Repository Pattern" [backend]  │
                     │   "All endpoints need auth" [api]     │
                     │   Scoped, weighted (must/should/may)  │
                     └───────────────┬──────────────────────┘
                                     │
               ┌─────────────────────┼─────────────────────┐
               │                     │                      │
       ┌───────▼──────┐     ┌───────▼──────┐     ┌────────▼─────┐
       │  Task T-001  │     │  Task T-002  │     │  Task T-003  │
       │ Setup models │     │ JWT middleware│     │ Auth routes  │
       │ depends: []  │     │ depends:[001]│     │ depends:[002]│
       └───────┬──────┘     └───────┬──────┘     └────────┬─────┘
               │                     │                      │
               ▼                     ▼                      ▼
         Code + Decide         Code + Decide          Code + Decide
         + Guidelines ✓        + Guidelines ✓         + Guidelines ✓
         Record changes        Record changes         Record changes
         Run gates             Run gates               Run gates
               │                     │                      │
               └─────────────────────┼─────────────────────┘
                                     │
                     ┌───────────────▼──────────────────────┐
                     │   /compound  →  Lessons extracted     │
                     │   Patterns, insights, validated       │
                     │   decisions — feed the next project   │
                     └──────────────────────────────────────┘
```

---

## Key Differentiators

| Capability | Traditional AI Coding | With Forge |
|:-----------|:---------------------:|:----------:|
| Tracks **why** code changed | — | Reasoning traces on every change |
| Records architectural decisions | — | Provenance, alternatives, confidence |
| Validates before completion | — | Configurable gates (test, lint, secrets) |
| Learns across projects | — | Compound learning system |
| Supports parallel AI agents | — | Conflict detection + dependency DAG |
| Project-wide coding standards | — | Scoped guidelines injected into task context |
| Enforces structured workflow | — | Contract-first pipeline |
| Hierarchical idea staging | — | Ideas mature before becoming tasks |
| Risk assessment built-in | — | 5D risk + feasibility analysis |

---

## Quick Start

```bash
# Clone Forge into your project
git clone https://github.com/ForgePrime/forge.git

# Inside Claude Code — start building
/idea Add user authentication            # Stage an idea
/discover I-001                           # Explore options, assess risks
/plan I-001                               # Create task graph (draft → approve)
/guideline Use Repository Pattern --scope backend  # Set coding standards
/next                                     # Execute first task (guidelines auto-loaded)
/status                                   # Project dashboard
```

For existing codebases, run **`/onboard`** first to import project knowledge.

---

## Architecture

```
forge/
├── core/           Python engine — pipeline, decisions, changes, gates, lessons
├── skills/         Built-in analysis skills (plan, discover, review, deep-*)
├── .claude/        Claude Code integration (15+ slash commands, hooks)
└── forge_output/   Runtime state (per-project JSON, gitignored)
```

**Design principle:** Python handles I/O and validation. The LLM handles judgment and code generation. The boundary is strict — Python never decides *what* to change, the LLM never writes state directly.

---

## Built-in Analysis Skills

Forge ships with deep analysis capabilities adapted from [Deep-Process](https://github.com/Deep-Process/deep-process):

| Skill | Purpose |
|:------|:--------|
| **deep-explore** | Structured option exploration with consequence tracing |
| **deep-risk** | 5-dimensional risk assessment with cascade analysis |
| **deep-feasibility** | 10-dimension feasibility study with GO/NO-GO verdict |
| **deep-architect** | Architecture design with 8 adversarial challenges |
| **deep-verify** | Artifact verification with impossibility pattern matching |
| **deep-requirements** | Requirements extraction and contradiction checking |

Invoked automatically via `/discover` or manually as needed. All findings flow into the decision log with full provenance.

---

## Get Involved

- **Report issues** — [GitHub Issues](https://github.com/ForgePrime/forge/issues)
- **Discuss ideas** — [GitHub Discussions](https://github.com/ForgePrime/forge/discussions)
- **Contribute** — see the [contributing guide](https://github.com/ForgePrime/forge/blob/main/CONTRIBUTING.md)

---

<p align="center">
  <img src="https://raw.githubusercontent.com/ForgePrime/.github/main/assets/ico.png" alt="ForgePrime" width="32"/><br/>
  <sub>Built with precision. Every change has a reason.</sub>
</p>
