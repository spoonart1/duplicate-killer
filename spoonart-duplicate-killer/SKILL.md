---
name: spoonart-duplicate-killer
description: General-purpose skill to audit, analyze, and eliminate duplicate or overlapping skills across multi-agent systems. Quantifies context window token waste, resolves instruction collisions, and executes lossless skill consolidation.
metadata:
  version: "2.0.0"
  type: "meta-engineering"
---

# Duplicate Skill Killer & Context Optimizer

This skill systematically audits multi-agent workspaces to detect, measure, and eliminate redundant skill files. It reduces system prompt token overhead, prevents conflicting agent instructions, and consolidates fragmented domain skills into high-density master skills.

## 1. When to Use
- An agent repository contains multiple skills covering overlapping domains (e.g., several copywriting, styling, testing, or API integration skills).
- Agent response latency increases or context windows degrade due to oversized system prompts.
- Agents display contradictory behaviors caused by conflicting directives in attached skills.
- Auditing a repository before scaling an agent squad.

## 2. The Context Bloat Problem
When multiple skills with overlapping instructions load into an agent's context window:
1. **Token Inefficiency:** Redundant rules (e.g., repeated style bans, identical formatting guides) consume 40% to 70% of available instruction tokens.
2. **Instruction Collision:** Small variations in overlapping guidelines cause model hesitation, nondeterministic outputs, or hallucinations.
3. **Maintenance Debt:** Updating a project standard requires editing multiple scattered skill files.

## 3. Four-Dimensional Overlap Analysis

Evaluate any candidate skill pair across four dimensions:

### 3.1 Lexical & Semantic Redundancy
- Compare banned word lists, stylistic rules, tone definitions, and formatting directives.
- Example: Skill A bans passive voice and AI buzzwords. Skill B bans passive voice, adverbs, and throat-clearing openers. Overlap is 80%.

### 3.2 Constraint & Threshold Duplication
- Compare technical thresholds, validation gates, and performance rules.
- Example: Skill A mandates GPU-only animations (`transform`, `opacity`). Skill B bans animating `width`, `height`, `top`, `left`. These rules are 100% functionally identical.

### 3.3 Tool & Resource Redundancy
- Inspect MCP tools, CLI commands, scripts, and API wrappers declared in each skill.
- Example: Two separate skills wrapping the same database query CLI or file search utilities.

### 3.4 Artifact Output Overlap
- Identify skills that output the same file types or schema structures (e.g., multiple skills generating metadata, JSON-LD schemas, or test scaffolding).

## 4. Context Waste Quantification Formula

Calculate the redundancy ratio for any skill cluster:

$$\text{Overlap Ratio (\%)} = \left( \frac{\text{Shared Directives}}{\text{Total Unique Directives}} \right) \times 100$$

$$\text{Token Savings} = \text{Combined Source Tokens} - \text{Consolidated Master Tokens}$$

- **Threshold for Action:** Any cluster with an Overlap Ratio $\ge 50\%$ must be flagged for consolidation.

## 5. The 5-Step Execution Protocol

```
[1. SCAN & PROFILE] ──► [2. PAIRWISE MATRIX] ──► [3. AUDIT REPORT (GATE)]
                                                           │
                                                           ▼ (User Confirms)
[5. VERIFY & CLEAN] ◄── [4. LOSSLESS MERGE] ◄──────────────┘
```

### Step 1: Scan & Token Profile
1. Recursively find all `SKILL.md` files in `.agents/skills/`, `.github/`, `.cursor/rules/`, or root configs.
2. Calculate word count and estimated token size for each skill.
3. Parse agent definitions to map which agents load which skills.

### Step 2: Pairwise Comparison Matrix
1. Group discovered skills into domain buckets:
   - Copywriting / Prose / Microcopy
   - UI / Design Systems / Accessibility / Animation
   - Technical Search / Structured Data / GEO / SEO
   - Code Quality / Testing / Architecture / DevOps
2. Compute the Overlap Ratio for each bucket.
3. Flag clusters exceeding the 50% redundancy threshold.

### Step 3: Pre-Merge Audit Report (Mandatory User Gate)
Never modify or delete skills before presenting the report to the user. The report must contain:
- Inventory of audited skills with token counts.
- Overlap percentage per domain cluster.
- Detailed listing of redundant rules and duplicated phrases.
- Proposed consolidated master skill names.
- Projected token savings per agent turn.
- A clear confirmation prompt.

### Step 4: Lossless Synthesis Engine
Upon receiving user approval, synthesize the master skill following these rules:
1. **Preserve Concrete Facts:** Keep all exact thresholds, numbers, regex patterns, code snippets, hardware specs, and edge-case exceptions.
2. **Deduplicate Prose:** Combine overlapping lists into a single consolidated reference table.
3. **Apply High Density:** Eliminate conversational filler, redundant introductions, and passive explanations.
4. **Standard Frontmatter:** Generate valid YAML frontmatter with precise name and description triggers.

### Step 5: Agent Rebinding & Verification
1. Update agent configurations to bind only the new consolidated skill.
2. Remove legacy redundant skills or move them to an archive directory.
3. Verify that all referenced markdown paths exist and use valid links.

## 6. Universal Audit Report Template

```markdown
# Agent Skill Redundancy & Context Audit Report

### Executive Summary
- Total Skills Audited: [Count]
- Identified Overlap Clusters: [Count]
- Current Token Overhead: ~[X] tokens per turn
- Projected Token Savings: ~[Y] tokens ([Z]% reduction)

### Redundancy Breakdown by Cluster

#### Cluster: [Domain Name] (Overlap: [X]%)
- Evaluated Skills: `skill-a`, `skill-b`, `skill-c`
- Redundant Directives:
  1. [Specific rule or restriction duplicated across skills]
  2. [Specific check or threshold duplicated across skills]
- Unique Elements to Retain:
  - From `skill-a`: [Unique constraint or spec]
  - From `skill-b`: [Unique tool or pattern]
- Proposed Master Skill: `[prefix]-[domain]`

### Proposed Agent Skill Reassignment
| Agent Name | Current Attached Skills | Proposed Consolidated Skill |
| :--- | :--- | :--- |
| [agent-1] | `skill-a`, `skill-b`, `skill-c` | `[prefix]-[domain]` |

### Action Required
Confirm to generate the consolidated master skills and update agent configuration files.
```

## 7. Quality Standards
- No em dashes. Use clean periods or simple punctuation.
- Active voice with direct subjects and verbs.
- All file references must use absolute paths or clickable markdown links.
