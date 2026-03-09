<p align="center">
  <img src="https://raw.githubusercontent.com/ForgePrime/.github/main/assets/forge-banner.png" alt="ForgePrime" width="800"/>
</p>

<h1 align="center">ForgePrime</h1>

<p align="center">
  <strong>Structured AI Development with Full Traceability</strong><br/>
  Every code change planned, tracked, reasoned about, and auditable.
</p>

<p align="center">
  <a href="https://github.com/ForgePrime/forge"><img src="https://img.shields.io/badge/forge-core-blue?style=for-the-badge&logo=github" alt="Forge Core"/></a>
  <a href="https://github.com/ForgePrime/forge/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-green?style=for-the-badge" alt="License"/></a>
  <a href="https://github.com/ForgePrime/forge/stargazers"><img src="https://img.shields.io/github/stars/ForgePrime/forge?style=for-the-badge&color=yellow" alt="Stars"/></a>
</p>

---

## The Problem

AI coding assistants generate code fast — but without structure. There is no audit trail, no decision history, no way to answer **"why was this done?"** six months later. Teams lose visibility, reviewers lose context, and technical debt compounds silently.

## Our Solution

**Forge** is a structured change orchestrator for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). It wraps AI-driven development in a rigorous process:

```
Idea  →  Discover  →  Plan  →  Execute  →  Validate  →  Record
```

Every step produces traceable artifacts — decisions with provenance, changes with reasoning traces, and validation gates that enforce quality before completion.

---

## What Forge Delivers

<table>
<tr>
<td width="50%" valign="top">

### For Engineering Teams

- **Decision Log** — every architectural choice recorded with alternatives considered, reasoning, and who decided (human vs AI)
- **Change Traceability** — every file modification linked to a task, decision, and reasoning trace
- **Validation Gates** — tests, lint, and secret scanning run automatically before task completion
- **Compound Learning** — lessons from past projects inform future ones across your organization

</td>
<td width="50%" valign="top">

### For Engineering Leaders

- **Full Audit Trail** — answer "why was this built this way?" at any time
- **Risk Visibility** — 5-dimensional risk assessment with severity, likelihood, and mitigation plans
- **Resumability** — interrupt and resume at any point; state persists in structured JSON
- **Multi-Agent Support** — multiple AI agents working in parallel with conflict detection

</td>
</tr>
</table>

---

## How It Works

```
                    ┌─────────────────────────────────────────┐
                    │              USER INTENT                 │
                    │         "Add JWT auth to API"            │
                    └──────────────┬──────────────────────────┘
                                   │
                    ┌──────────────▼──────────────────────────┐
                    │  /idea  →  /discover  →  /plan          │
                    │  Stage ideas, explore options, assess    │
                    │  risks, decompose into task graph        │
                    └──────────────┬──────────────────────────┘
                                   │
              ┌────────────────────┼────────────────────┐
              │                    │                     │
      ┌───────▼───────┐   ┌───────▼───────┐   ┌────────▼──────┐
      │   Task T-001  │   │   Task T-002  │   │   Task T-003  │
      │  Setup models │   │  JWT middleware│   │  Auth routes  │
      │  depends: []  │   │  depends:[001]│   │  depends:[002]│
      └───────┬───────┘   └───────┬───────┘   └────────┬──────┘
              │                    │                     │
              ▼                    ▼                     ▼
        Code + Decide        Code + Decide         Code + Decide
        Record changes       Record changes        Record changes
        Run gates            Run gates              Run gates
              │                    │                     │
              └────────────────────┼────────────────────┘
                                   │
                    ┌──────────────▼──────────────────────────┐
                    │  /compound  →  Lessons extracted         │
                    │  Patterns, mistakes, validated decisions  │
                    └─────────────────────────────────────────┘
```

---

## Key Differentiators

| Capability | Traditional AI Coding | Forge |
|:-----------|:---------------------:|:-----:|
| Tracks **why** code changed | - | **Yes** — reasoning traces on every change |
| Records architectural decisions | - | **Yes** — with provenance and alternatives |
| Validates before completion | - | **Yes** — configurable gates (test, lint, secrets) |
| Learns across projects | - | **Yes** — compound learning system |
| Supports parallel AI agents | - | **Yes** — with conflict detection |
| Enforces structured workflow | - | **Yes** — contract-first pipeline |
| Hierarchical idea staging | - | **Yes** — ideas mature before becoming tasks |
| Risk assessment built-in | - | **Yes** — 5D risk + feasibility analysis |

---

## Quick Start

```bash
# Clone Forge into your project
git clone https://github.com/ForgePrime/forge.git

# Inside Claude Code — start building
/idea Add user authentication            # Stage an idea
/discover I-001                           # Explore options, assess risks
/plan I-001                               # Create task graph (draft → approve)
/next                                     # Execute first task with full traceability
/status                                   # Project dashboard
```

For existing codebases, run `/onboard` first to import project knowledge.

---

## Architecture at a Glance

```
forge/
├── core/           Python engine — pipeline, decisions, changes, gates, lessons
├── skills/         Built-in analysis skills (plan, discover, review, deep-*)
├── .claude/        Claude Code integration (15+ slash commands, hooks)
└── forge_output/   Runtime state (per-project JSON, gitignored)
```

**Design principle:** Python handles I/O and validation. The LLM handles judgment and code generation. The boundary is strict — Python never decides *what* to change, and the LLM never writes state directly.

---

## Built-in Analysis Skills

Forge ships with deep analysis capabilities adapted from [Deep-Process](https://github.com/Deep-Process/deep-process):

| Skill | What It Does |
|:------|:-------------|
| **deep-explore** | Structured option exploration with consequence tracing |
| **deep-risk** | 5-dimensional risk assessment with cascade analysis |
| **deep-feasibility** | 10-dimension feasibility study with GO/NO-GO verdict |
| **deep-architect** | Architecture design with 8 adversarial challenges |
| **deep-verify** | Artifact verification with impossibility pattern matching |
| **deep-requirements** | Requirements extraction and contradiction checking |

These are invoked automatically during `/discover` or manually as needed. All findings flow into the decision log with full provenance.

---

## Repositories

| Repository | Description | Status |
|:-----------|:------------|:------:|
| [**forge**](https://github.com/ForgePrime/forge) | Core orchestrator — pipeline, decisions, changes, gates, learning | Active |

---

## Contributing

We welcome contributions. See the [contributing guide](https://github.com/ForgePrime/forge/blob/main/CONTRIBUTING.md) for details.

- **Report issues** — [GitHub Issues](https://github.com/ForgePrime/forge/issues)
- **Discuss ideas** — [GitHub Discussions](https://github.com/ForgePrime/forge/discussions)

---

<p align="center">
  <sub>Built with precision. Every change has a reason.</sub>
</p>
