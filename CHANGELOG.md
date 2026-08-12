# Changelog

## [0.7.0-draft] — 2026-08-12

### Added — AI Advice

- Added new `ai-advice` skill as a general technical setup advisor.
- Added support for technical setup, software installation, configuration,
  deployment, infrastructure setup, technical integration, troubleshooting,
  validation, and technical platform recommendation.
- Added four working modes:
  - Advisor Mode;
  - Setup Mode;
  - Troubleshooting Mode;
  - Validation Mode.
- Added modular references for:
  - Hostinger;
  - Linux/Ubuntu;
  - OpenRouter;
  - Discord;
  - GitHub;
  - ETAP;
  - database;
  - deployment;
  - API integration;
  - security.
- Added reusable templates for:
  - platform comparison;
  - setup checklist;
  - troubleshooting;
  - validation.

### Changed — routing and package consistency

- Updated `ai-advice` routing from broad keyword-based activation to
  **primary-intent-based routing**.
- Added negative routing rules so technical keywords such as `API`, `GitHub`,
  `server`, `database`, `OpenRouter`, `Linux`, or `error` do not automatically
  trigger AI Advice.
- Clarified routing boundaries between `ai-advice` and:
  - `indonesia-business-modeler`;
  - `business-excellence-assessor`;
  - `indonesia-corporate-action-intelligence`;
  - `persona`;
  - `book-writer`.
- Updated `docs/skill-routing-matrix.md` to include AI Advice and cross-skill
  conflict examples.
- Standardized folder naming from `indonesia-business-modeler 2` to
  `indonesia-business-modeler`.
- Standardized skill frontmatter to improve validator compatibility.
- Updated root `README.md` from five skills to six skills.
- Updated package version from `0.6.0-draft` to `0.7.0-draft`.
- Clarified GitHub as the package source of truth and Hermes as the runtime
  environment.

### Validation

- Revised skill frontmatter passes static validation in the current workspace.
- AI Advice structure, references, and templates have been added to the package.
- Behavioral validation is still required for:
  - explicit skill invocation;
  - automatic routing;
  - negative routing;
  - cross-skill conflict handling;
  - Advisor Mode;
  - Setup Mode;
  - Troubleshooting Mode;
  - Validation Mode;
  - multi-user routing consistency through Hermes/Discord.

### Status

Draft.

Package structure has been updated to `0.7.0-draft`, but behavioral and
multi-user tests must still be completed before release-candidate or
production-ready status.

---

## [0.6.0-draft] — 2026-07-27

### Changed — all skills reviewed

- Audited five skills for scope, routing, source discipline, completeness,
  templates, references, and tests.
- Standardized all skill versions to 1.0.0-draft inside package 0.6.0-draft.
- Added or expanded skill-level changelogs and tests.

### Indonesia Business Modeler

- Replaced the narrow IRR-centered mode with complete Investment Feasibility
  Analysis.
- Added NPV, IRR, ROI, ARR, BEP Unit, BEP Sales, Payback Period, Discounted
  Payback Period, Profitability Index, scenario analysis, and sensitivity.
- Corrected Profitability Index logic.
- Added financial-model integrity checks.
- Preserved the old IRR template path as a compatibility alias.

### Indonesia Corporate Action Intelligence

- Added CNBC International/CNBC.com as Tier 2B international source.
- Kept CNBC Indonesia as Tier 2A local source.
- Enforced strict four-sector boundary in Rekind Sector Intelligence Brief.
- Added bilingual search, selection gate, transmission path, deeper sector
  analysis, and expanded HTML template.

### Business Excellence Assessor

- Added implementation rubric and recommendation-prioritization guides.
- Prevented approach-only evidence from being treated as managed/optimized
  implementation.
- Expanded routing for all financial feasibility metrics.

### Persona

- Added Fast Build mode, completeness criteria, and package routing.
- Reduced unnecessary clarification when language/context is already clear.

### Book Writer

- Added source traceability and publication QA assets.
- Added minimum deliverables per mode and long-book consistency controls.

### Documentation and validation

- Added package routing matrix, release notes, full audit report, VERSION file,
  regenerated file manifest, and static validation report.

### Status

Draft. Behavioral tests in Claude remain NOT TESTED.

---

## [0.5.0-draft] — 2026-07-27

- Added Business Excellence Assessor.

---

## [0.4.0-draft] — 2026-07-24

- Added Mode K and initial IRR/cash-flow/business-opportunity improvements.

---

## [0.3.0-draft] — 2026-07-22

- Natural-language and structure revision.