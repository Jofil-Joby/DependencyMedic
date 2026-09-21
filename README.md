# DependencyMedic

> Portable agent for detecting missing or unclear dependency manifests and improving dependency hygiene.

## What it does

DependencyMedic inspects project structure and checks whether a recognizable dependency manifest is present. It turns a small but important piece of repository evidence into an explainable recommendation.

### Diagnostic fingerprint

**Manifest discovery → dependency signal → evidence → action**

It recognizes common ecosystems such as npm, Python, Maven, and Gradle through their manifest files.

## Why this agent is distinct

DependencyMedic is deliberately focused on the dependency boundary of a project. It does not claim to solve every supply-chain problem. Its purpose is to establish whether the project exposes a clear source of dependency declarations that other automation can inspect.

That narrow scope makes the agent easy to compose with security, packaging, and deployment diagnostics.

## Passport architecture

```text
Project tree
   ↓
Manifest detector
   ↓
Dependency diagnostic rule
   ↓
Evidence-backed finding
   ↓
Improvement plan
```

The passport defines the identity and behavior contract, while the checker owns the domain-specific signal.

## Verification

Included in this repository:
- OpenGAP-compatible `agent.yaml`
- behavior contract in `SOUL.md`
- explainability contract
- four portability adapters
- dependency-focused broken-project fixture
- adapter verification tests

The OpenGAP validator and four framework exports have been exercised successfully.

## Repository layout

```text
agent.yaml / SOUL.md / EXPLAINABILITY.md
AGENTS.md / DUTIES.md
agent.py
tools/scanner.py
tools/checker.py
adapters/
tests/
```

## Design principle

**Declare what the project actually exposes.** DependencyMedic does not invent package information. It checks for visible project evidence and recommends the next step when that evidence is missing.

## Medic family

DependencyMedic is a focused component in a larger set of portable engineering agents. The common passport contract gives the family consistency; the diagnostic rule gives each member its own purpose.