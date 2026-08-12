# Release Notes — v0.7.0-draft

## Overview

Version `0.7.0-draft` introduces **AI Advice** as a new general technical setup advisor and improves routing consistency across the skill package.

This release focuses on:

- adding a new technical setup capability;
- improving cross-skill routing;
- standardizing skill naming and frontmatter;
- updating package documentation;
- preparing the package for broader behavioral testing in Hermes and Discord.

## New Skill — AI Advice

`ai-advice` is designed to help users with:

- technical setup;
- software installation;
- configuration;
- deployment;
- infrastructure setup;
- technical integration;
- troubleshooting;
- validation;
- technical platform recommendation.

AI Advice is not limited to AI-related tools.

Example supported use cases include:

- Hostinger / VPS;
- Linux / Ubuntu;
- OpenRouter;
- Discord Bot;
- GitHub;
- ETAP;
- database setup;
- application deployment;
- API integration;
- technical troubleshooting.

## AI Advice Working Modes

AI Advice provides four working modes:

1. **Advisor Mode**
   - identifies requirements;
   - compares options;
   - recommends the most suitable technical approach;
   - explains trade-offs and risks.

2. **Setup Mode**
   - provides sequential setup instructions;
   - explains expected results;
   - validates important steps;
   - provides fallback guidance when a step fails.

3. **Troubleshooting Mode**
   - identifies symptoms;
   - determines likely root causes;
   - performs diagnostic checks;
   - applies the smallest reasonable fix;
   - validates the result.

4. **Validation Mode**
   - verifies installation;
   - configuration;
   - connectivity;
   - integration;
   - security controls;
   - persistent operation where relevant.

## AI Advice Structure

The skill uses a modular structure:

```text
skills/ai-advice/
├── SKILL.md
├── README.md
├── references/
│   ├── api-integration.md
│   ├── database.md
│   ├── deployment.md
│   ├── discord.md
│   ├── etap.md
│   ├── github.md
│   ├── hostinger.md
│   ├── linux-ubuntu.md
│   ├── openrouter.md
│   └── security.md
└── templates/
    ├── comparison-template.md
    ├── setup-checklist.md
    ├── troubleshooting-template.md
    └── validation-checklist.md
```

## Routing Improvements

Routing has been revised to prioritize the user's **primary intent** instead of relying only on keywords.

AI Advice should activate when the primary intent involves:

- technical setup;
- installation;
- configuration;
- deployment;
- infrastructure;
- technical integration;
- troubleshooting;
- validation;
- technical platform recommendation.

AI Advice should not automatically activate only because the prompt contains words such as:

- API;
- GitHub;
- server;
- database;
- OpenRouter;
- Linux;
- error.

Cross-skill boundaries were clarified between:

- `ai-advice`;
- `indonesia-business-modeler`;
- `business-excellence-assessor`;
- `indonesia-corporate-action-intelligence`;
- `persona`;
- `book-writer`.

Example:

> “OpenRouter error saat menjalankan Business Modeler.”

Primary intent: technical troubleshooting  
→ `ai-advice`

> “Analisis model bisnis perusahaan yang menggunakan OpenRouter.”

Primary intent: business analysis  
→ `indonesia-business-modeler`

## Repository Improvements

The following repository changes are included:

- added `ai-advice`;
- standardized `indonesia-business-modeler` folder naming;
- removed the previous `indonesia-business-modeler 2` naming;
- standardized skill frontmatter;
- updated the package routing matrix;
- updated the root README;
- updated package version to `0.7.0-draft`;
- updated the package changelog.

## Source of Truth

GitHub is used as the source of truth for the latest skill version.

Development flow:

```text
Claude
→ generate / review / brainstorming

VS Code
→ final editing

GitHub
→ version control and source of truth

Hermes
→ runtime

Discord
→ multi-user interface
```

Changes in Claude Project do not automatically update GitHub or Hermes.

## Validation Status

Static validation has been completed for the revised frontmatter and current repository structure.

Behavioral testing is still required for:

- explicit skill invocation;
- automatic routing;
- negative routing;
- cross-skill conflict handling;
- Advisor Mode;
- Setup Mode;
- Troubleshooting Mode;
- Validation Mode;
- unknown-platform handling;
- security behavior;
- multi-user routing consistency through Hermes/Discord.

## Release Status

`0.7.0-draft`

This package is still in **draft** status.

The package must not be considered release-candidate or production-ready until behavioral tests and multi-user consistency tests have been completed and documented.