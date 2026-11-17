# Duplicate Killer (`spoonart-duplicate-killer`)

**Duplicate Killer** is a meta-engineering skill designed to audit, analyze, and eliminate duplicate or overlapping skills and instructions across multi-agent systems (including Google Antigravity, Cursor, Claude Code, and other AI agent architectures).

---

## 🚀 How to Install

You can install this skill into your local project workspace or globally across your agent environment.

### Option 1: Workspace Installation (Recommended)

Clone the repository directly into your project's agent skills directory:

```bash
# For Google Antigravity / agent workflows (.agents/skills or .gemini/skills)
mkdir -p .agents/skills
git clone https://github.com/spoonart1/duplicate-killer.git .agents/skills/spoonart-duplicate-killer
```

### Option 2: Global Installation (Google Antigravity)

To make `spoonart-duplicate-killer` available across all workspaces on your machine:

```bash
git clone https://github.com/spoonart1/duplicate-killer.git ~/.gemini/config/skills/spoonart-duplicate-killer
```

### Option 3: Manual Integration (Cursor / Claude Code / Custom Agents)

Copy or symlink [spoonart-duplicate-killer/SKILL.md](file:///Volumes/Work/skills-collection/spoonart-duplicate-killer/SKILL.md) into your agent configuration directory:
- **Google Antigravity:** `.agents/skills/spoonart-duplicate-killer/SKILL.md`
- **Cursor:** `.cursor/rules/duplicate-killer.mdc`
- **Claude Code:** `.claude/skills/duplicate-killer/SKILL.md`

---

## 💡 How to Use

Once installed, trigger the audit by instructing your agent in chat:

> *"Audit all skills in this repository for duplicates and token overlap using `spoonart-duplicate-killer`."*

The skill will run the 5-step execution protocol, quantify token savings, and present an audit report before applying any changes.

---

## 🎯 Key Objectives

- **Reduce Context Window Token Overhead:** Cut instruction prompt token waste by 40% to 70% by eliminating redundant rules and duplicated guidance.
- **Prevent Instruction Collisions:** Resolve contradictory directives between overlapping skills that cause model hesitation, nondeterministic outputs, or hallucinations.
- **Lossless Skill Consolidation:** Merge fragmented domain skills into high-density master skills while preserving all technical thresholds, regex patterns, code snippets, hardware specifications, and critical edge cases.

---

## 🔍 Four-Dimensional Overlap Analysis

Skills are evaluated for redundancy across four key dimensions:

1. **Lexical & Semantic Redundancy:** Compares banned word lists, style guidelines, tone definitions, and formatting directives.
2. **Constraint & Threshold Duplication:** Identifies functionally identical performance rules, validation gates, and technical thresholds.
3. **Tool & Resource Redundancy:** Audits duplicated MCP tools, CLI command wrappers, helper scripts, and API bindings.
4. **Artifact Output Overlap:** Detects skills generating identical file types, schemas, or output structures.

---

## ⚡ 5-Step Execution Protocol

```
[1. SCAN & PROFILE] ──► [2. PAIRWISE MATRIX] ──► [3. AUDIT REPORT (GATE)]
                                                           │
                                                           ▼ (User Approval)
[5. VERIFY & CLEAN] ◄── [4. LOSSLESS MERGE] ◄──────────────┘
```

1. **Scan & Token Profile:** Recursively scan skill directories (`SKILL.md`, rules) and estimate token footprint per turn.
2. **Pairwise Comparison Matrix:** Group skills into domain buckets and calculate the Overlap Ratio. Clusters with an overlap of 50% or higher are flagged for consolidation.
3. **Pre-Merge Audit Report (Mandatory Gate):** Present a comprehensive audit report with projected token savings to the user before modifying any files.
4. **Lossless Synthesis Engine:** Synthesize high-density master skills by stripping conversational filler and deduplicating prose without losing concrete facts.
5. **Agent Rebinding & Verification:** Rebind agent configurations to the new master skills and safely archive legacy redundant files.

---

## 📁 Repository Structure

- [spoonart-duplicate-killer/SKILL.md](file:///Volumes/Work/skills-collection/spoonart-duplicate-killer/SKILL.md): Full skill specification and operational instructions.
- [spoonart-duplicate-killer/README.md](file:///Volumes/Work/skills-collection/spoonart-duplicate-killer/README.md): Quick reference and installation links.
