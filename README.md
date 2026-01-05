<div align="center">

<!-- Animated Typing Banner -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=3000&pause=1000&color=2E9EF7&center=true&vCenter=true&multiline=true&repeat=true&width=600&height=100&lines=UX+Design+Assistant;7+Agents+%7C+7+Skills;Claude+Code+Plugin" alt="UX Design Assistant" />

<br/>

<!-- Badge Row 1: Status Badges -->
[![Version](https://img.shields.io/badge/Version-1.1.0-blue?style=for-the-badge)](https://github.com/pluginagentmarketplace/custom-plugin-ux-design/releases)
[![License](https://img.shields.io/badge/License-Custom-yellow?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Production-brightgreen?style=for-the-badge)](#)
[![SASMP](https://img.shields.io/badge/SASMP-v1.3.0-blueviolet?style=for-the-badge)](#)

<!-- Badge Row 2: Content Badges -->
[![Agents](https://img.shields.io/badge/Agents-7-orange?style=flat-square&logo=robot)](#-agents)
[![Skills](https://img.shields.io/badge/Skills-7-purple?style=flat-square&logo=lightning)](#-skills)
[![Commands](https://img.shields.io/badge/Commands-4-green?style=flat-square&logo=terminal)](#-commands)

<br/>

<!-- Quick CTA Row -->
[**Install Now**](#-quick-start) | [**Explore Agents**](#-agents) | [**Documentation**](#-documentation)

---

### What is this?

> **UX Design Assistant** is a production-grade Claude Code plugin with **7 specialized agents** and **7 atomic skills** for comprehensive UX design workflows.

</div>

---

## Table of Contents

- [Quick Start](#-quick-start)
- [Features](#-features)
- [Agents](#-agents)
- [Skills](#-skills)
- [Commands](#-commands)
- [Architecture](#-architecture)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)

---

## Quick Start

### Prerequisites

- Claude Code CLI v2.0.27+
- Active Claude subscription

### Installation

**Option 1: From Marketplace (Recommended)**
```bash
/plugin marketplace add pluginagentmarketplace/custom-plugin-ux-design
/plugin install custom-plugin-ux-design@pluginagentmarketplace-ux-design
```

**Option 2: Local Installation**
```bash
git clone https://github.com/pluginagentmarketplace/custom-plugin-ux-design.git
cd custom-plugin-ux-design
/plugin load .
```

### Verify Installation

After restart, you should see these agents:
```
custom-plugin-ux-design:01-ux-research
custom-plugin-ux-design:02-ui-design
custom-plugin-ux-design:03-interaction-design
custom-plugin-ux-design:04-prototyping
custom-plugin-ux-design:05-accessibility
custom-plugin-ux-design:06-mobile-ux
custom-plugin-ux-design:07-ux-writing
```

---

## Features

| Feature | Description |
|---------|-------------|
| **7 Production-Grade Agents** | Specialized AI agents with clear boundaries, I/O schemas, error handling |
| **7 Atomic Skills** | Single-responsibility skills with validation, retry logic, test templates |
| **4 Workflow Commands** | Comprehensive slash commands for plugin development |
| **SASMP v1.3.0** | Full protocol compliance with EQHM enabled |
| **Troubleshooting Guides** | Decision trees and debug checklists for every component |

---

## Agents

### 7 Specialized UX Design Agents

| # | Agent | Purpose | Bonded Skill |
|---|-------|---------|--------------|
| 1 | **01-ux-research** | User interviews, surveys, personas, journey mapping, usability testing | `user-research` |
| 2 | **02-ui-design** | Visual design, design systems, components, typography, color theory | `ui-design` |
| 3 | **03-interaction-design** | Interaction patterns, micro-interactions, user flows, affordances | `interaction-design` |
| 4 | **04-prototyping** | Figma workflows, wireframes, interactive prototypes, user testing | `prototyping` |
| 5 | **05-accessibility** | WCAG compliance, screen readers, keyboard navigation, inclusive design | `accessibility` |
| 6 | **06-mobile-ux** | iOS HIG, Material Design, gestures, responsive patterns | `mobile-ux` |
| 7 | **07-ux-writing** | Microcopy, voice and tone, error messages, CTAs, content strategy | `ux-writing` |

### Agent Features (Production-Grade)

Each agent includes:
- Clear role & responsibility boundaries
- Type-safe input/output schemas
- Error handling with recovery strategies
- Fallback mechanisms
- Token/cost optimization configs
- Troubleshooting decision trees

---

## Skills

### 7 Atomic Skills

| Skill | Description | Invoke |
|-------|-------------|--------|
| `user-research` | Master user research methods and analysis | `Skill("custom-plugin-ux-design:user-research")` |
| `ui-design` | Master visual design and design systems | `Skill("custom-plugin-ux-design:ui-design")` |
| `interaction-design` | Master interaction patterns and micro-interactions | `Skill("custom-plugin-ux-design:interaction-design")` |
| `prototyping` | Master wireframing and prototype testing | `Skill("custom-plugin-ux-design:prototyping")` |
| `accessibility` | Master WCAG compliance and inclusive design | `Skill("custom-plugin-ux-design:accessibility")` |
| `mobile-ux` | Master iOS HIG and Material Design | `Skill("custom-plugin-ux-design:mobile-ux")` |
| `ux-writing` | Master microcopy and content strategy | `Skill("custom-plugin-ux-design:ux-writing")` |

### Skill Features (Production-Grade)

Each skill includes:
- Atomic, single-responsibility design
- Comprehensive parameter validation
- Retry logic with exponential backoff
- Logging & observability hooks
- Unit test templates
- Learning modules

---

## Commands

| Command | Description | Usage |
|---------|-------------|-------|
| `/create-plugin` | Create new Claude Code plugin with scaffolding | `/create-plugin my-plugin --scaffold` |
| `/design-ux` | Design UX with research, wireframes, prototypes | `/design-ux my-plugin --research` |
| `/market-plugin` | Market research and growth strategy | `/market-plugin my-plugin --strategy` |
| `/publish-plugin` | Validate and publish to marketplace | `/publish-plugin my-plugin --validate` |

---

## Architecture

### Dependency Graph

```
                    AGENT-SKILL ARCHITECTURE
================================================================

  AGENTS (Orchestration)              SKILLS (Atomic Execution)
  ─────────────────────               ───────────────────────────

  01-ux-research ─────────────────── user-research
       │
       ↓ (insights)
  02-ui-design ───────────────────── ui-design
       │
       ↓ (components)
  03-interaction-design ──────────── interaction-design
       │
       ↓ (patterns)
  04-prototyping ─────────────────── prototyping
       │
       ↓ (validation)
  05-accessibility ───────────────── accessibility
       │
       ↓ (compliance)
  06-mobile-ux ───────────────────── mobile-ux
       │
       ↓ (platform specs)
  07-ux-writing ──────────────────── ux-writing

================================================================
```

### Integrity Verification

```
INTEGRITY CHECK: PASSED
─────────────────────────────────────────
[OK] Agent → Skill bonds: 7/7 valid
[OK] Orphan skills: 0
[OK] Ghost triggers: 0
[OK] Circular dependencies: 0
[OK] All file references valid
─────────────────────────────────────────
```

---

## Troubleshooting

### Common Issues

#### Agent not responding
```
Check:
├── Is plugin loaded? Run: /plugin list
├── Is agent name correct? Check: agents/*.md
├── Are tools available? Verify model permissions
└── Resolution: Reload plugin
```

#### Skill invocation fails
```
Check:
├── Is skill name correct? Check: skills/*/SKILL.md
├── Are parameters valid? Check schema
├── Is bonded agent available?
└── Resolution: Check skill frontmatter
```

#### Command not found
```
Check:
├── Is command registered? Check: commands/*.md
├── Is path in plugin.json correct?
└── Resolution: Verify plugin.json commands array
```

---

## Project Structure

```
custom-plugin-ux-design/
├── .claude-plugin/
│   ├── plugin.json          # Plugin manifest
│   └── marketplace.json     # Marketplace config
├── agents/                   # 7 production-grade agents
│   ├── 01-ux-research.md
│   ├── 02-ui-design.md
│   ├── 03-interaction-design.md
│   ├── 04-prototyping.md
│   ├── 05-accessibility.md
│   ├── 06-mobile-ux.md
│   └── 07-ux-writing.md
├── skills/                   # 7 atomic skills
│   ├── user-research/SKILL.md
│   ├── ui-design/SKILL.md
│   ├── interaction-design/SKILL.md
│   ├── prototyping/SKILL.md
│   ├── accessibility/SKILL.md
│   ├── mobile-ux/SKILL.md
│   └── ux-writing/SKILL.md
├── commands/                 # 4 workflow commands
│   ├── create-plugin.md
│   ├── design-ux.md
│   ├── market-plugin.md
│   └── publish-plugin.md
├── hooks/
│   └── hooks.json
├── README.md
├── CHANGELOG.md
└── LICENSE
```

---

## Metadata

| Field | Value |
|-------|-------|
| **Version** | 1.1.0 |
| **Last Updated** | 2025-12-30 |
| **Status** | Production Ready |
| **SASMP** | v1.3.0 |
| **Agents** | 7 (Production-Grade) |
| **Skills** | 7 (Atomic Design) |
| **Commands** | 4 |

---

## Contributing

Contributions are welcome! Please read our [Contributing Guide](CONTRIBUTING.md).

1. Fork the repository
2. Create your feature branch
3. Follow production-grade standards for new agents/skills
4. Submit a pull request

---

## Security

> **Important:** This repository contains third-party code and dependencies.
>
> - Always review code before using in production
> - Check dependencies for known vulnerabilities
> - Follow security best practices
> - Report security issues privately via [Issues](../../issues)

---

## License

Copyright 2025 **Dr. Umit Kacar** & **Muhsin Elcicek**

Custom License - See [LICENSE](LICENSE) for details.

---

## Contributors

| Contributor | Role |
|-------------|------|
| **Dr. Umit Kacar** | Senior AI Researcher & Engineer |
| **Muhsin Elcicek** | Senior Software Architect |

---

<div align="center">

**Made for the Claude Code Community**

[![GitHub](https://img.shields.io/badge/GitHub-pluginagentmarketplace-black?style=for-the-badge&logo=github)](https://github.com/pluginagentmarketplace)

</div>
