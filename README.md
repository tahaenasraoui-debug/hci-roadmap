# Human-Computer Interaction (HCI) Roadmap

![License](https://img.shields.io/badge/license-MIT-green.svg) ![focus](https://img.shields.io/badge/focus-usability%20%2B%20accessibility-purple.svg) ![stack](https://img.shields.io/badge/stack-react%20%7C%20figma-informational.svg)

Design and build interfaces that people can actually use. Principles, visual design, accessibility, research methods, and implementation, with evidence from real users.

## Table of Contents

1. [Workflow Overview](#workflow-overview)
2. [Prerequisites](#prerequisites)
3. [Phase 1: Principles](#phase-1-principles)
4. [Phase 2: Visual & Interaction Design](#phase-2-visual--interaction-design)
5. [Phase 3: Accessibility](#phase-3-accessibility)
6. [Phase 4: Research Methods](#phase-4-research-methods)
7. [Phase 5: Build & Test the Interface](#phase-5-build--test-the-interface)
8. [Capstone Projects](#capstone-projects)
9. [Repository Layout](#repository-layout)
10. [Engineering Rules](#engineering-rules)
11. [Exit Criteria](#exit-criteria)

---

## Workflow Overview

```
 Principles --> Visual design --> Accessibility --> Research methods
                                                         |
 Ship + iterate <-- Build in React <-- Prototype (Figma) <+
        |
        +--> Usability test --> Fix --> Retest
```

## Prerequisites

- [ ] Basic HTML, CSS, and JavaScript
- [ ] Ability to recruit 5 test users (friends and classmates count)
- [ ] A free Figma account

## Phase 1: Principles

Goal: Learn why interfaces succeed or fail, in plain language.

| Resource | Type | Why |
|----------|------|-----|
| [Nielsen's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/) | Article | The standard evaluation checklist |
| [Laws of UX](https://lawsofux.com/) | Reference | Psychology principles behind design choices |
| [Don't Make Me Think](https://sensible.com/dont-make-me-think/) | Book | Short, practical web usability |
| [Magic Ink (Bret Victor)](http://worrydream.com/MagicInk/) | Essay | Information software as graphic design |
| [Human-Computer Interaction, Dix et al.](https://www.hcibook.com/e3/) | Textbook site | Academic grounding |

- [ ] Evaluate 5 real apps against the 10 heuristics
- [ ] Read Dix chapters on human factors, interaction design, and evaluation
- [ ] Write a one-page critique of an interface you use daily

**Deliverables**
- [ ] `research/heuristic_evals/` with 5 written evaluations

## Phase 2: Visual & Interaction Design

Goal: Make interfaces look clear without a designer.

| Resource | Type | Why |
|----------|------|-----|
| [Refactoring UI](https://www.refactoringui.com/) | Book and tips | Hierarchy, spacing, color for developers |
| [Material Design 3](https://m3.material.io/) | Design system | Components and patterns |
| [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/) | Guidelines | Platform conventions |
| [Figma Help Center](https://help.figma.com/hc/en-us) | Docs | Prototyping and components |

- [ ] Redesign one screen of an app you dislike: before and after
- [ ] Build a Figma component set (buttons, inputs, cards) with states
- [ ] Define a type scale, spacing scale, and color palette

**Deliverables**
- [ ] `design/figma_links.md`
- [ ] `docs/design_tokens.md`

## Phase 3: Accessibility

Goal: Build interfaces that work for everyone, from the start.

| Resource | Type | Why |
|----------|------|-----|
| [WCAG Overview](https://www.w3.org/WAI/standards-guidelines/wcag/) | Standard | What conformance requires |
| [web.dev Learn Accessibility](https://web.dev/learn/accessibility) | Free course | Practical, short lessons |
| [axe DevTools](https://www.deque.com/axe/) | Tool | Automated accessibility testing |

- [ ] Navigate your own site with keyboard only and with a screen reader
- [ ] Fix every axe violation on one page
- [ ] Check color contrast on all text

**Deliverables**
- [ ] `docs/a11y_audit.md` with before and after results

## Phase 4: Research Methods

Goal: Replace opinions with observations.

| Resource | Type | Why |
|----------|------|-----|
| [Usability Testing 101](https://www.nngroup.com/articles/usability-testing-101/) | Article | How to run a test |
| [Just Enough Research](https://abookapart.com/products/just-enough-research) | Book | Lightweight user research |
| [System Usability Scale](https://www.usability.gov/how-to-and-tools/methods/system-usability-scale.html) | Method | Quantify perceived usability |
| [ACM CHI Proceedings](https://dl.acm.org/conference/chi) | Papers | Read 3 papers to see how HCI research is done |

- [ ] Write a test plan with 3 tasks and success criteria
- [ ] Run moderated tests with 5 users and record observations
- [ ] Score the SUS and compute time-on-task

**Deliverables**
- [ ] `research/test_report.md` with findings, severity ratings, and fixes
- [ ] 3 paper summaries in `research/papers/`

## Phase 5: Build & Test the Interface

Goal: Implement your designs and keep them from regressing.

| Resource | Type | Why |
|----------|------|-----|
| [React Learn](https://react.dev/learn) | Docs | Component-based UI |
| [Storybook](https://storybook.js.org/docs) | Docs | Develop and document components in isolation |
| [Playwright](https://playwright.dev/docs/intro) | Docs | End-to-end UI tests |

- [ ] Implement your Figma components in React with keyboard support and ARIA where needed
- [ ] Document each component in Storybook
- [ ] Add end-to-end tests for the main flow and an axe check in CI

**Deliverables**
- [ ] `src/components/` library with Storybook
- [ ] `tests/e2e/` Playwright suite

## Capstone Projects

- [ ] Redesign an existing app (a university portal is a good target), test the original and your version with 5 users each, and compare SUS scores
- [ ] Ship an accessible component library with documentation and automated a11y tests
- [ ] Write a 4-page research report with method, results, and limits

## Repository Layout

```
hci/
├── README.md
├── package.json
├── design/                   # Figma links, exports
├── src/
│   └── components/
├── .storybook/
├── tests/
│   └── e2e/                  # Playwright + axe
├── research/
│   ├── heuristic_evals/
│   ├── papers/
│   └── test_report.md
└── docs/
    ├── design_tokens.md
    └── a11y_audit.md
```

## Engineering Rules

These are strict. A phase is not complete until its deliverables follow all of them.

### 1. Daily 1:3 Theory-to-Building Ratio

- [ ] For every 1 hour of reading or watching, spend 3 hours building, solving, or running labs
- [ ] Log hours in `docs/log.md` at the end of each session
- [ ] No new chapter until the previous one has working code or a written lab report

### 2. Git Branch Hygiene

- [ ] `main` is always green and never receives direct commits
- [ ] One branch per deliverable: `phase-N/short-description`
- [ ] Small commits with imperative messages; squash-merge via PR after checks pass
- [ ] Delete branches after merge

### 3. Quality Gates

- [ ] TypeScript in strict mode (`tsc --noEmit`) passes
- [ ] `eslint` and `prettier --check` pass
- [ ] Playwright and axe checks pass in CI
- [ ] Lighthouse accessibility score of 95 or higher on key pages

### 4. Branch-Specific Rules

- [ ] Every design claim cites a heuristic, a test result, or a paper
- [ ] Test with real users before calling a design good; your own opinion does not count
- [ ] Informed consent for every test participant, and no personal data in the repo
- [ ] Accessibility is part of done: a feature without keyboard and screen-reader support is unfinished

## Exit Criteria

- [ ] Run a 5-user usability test and report prioritized findings
- [ ] Fix an interface's accessibility failures and prove it with measurements
- [ ] Justify a design decision with evidence rather than taste
- [ ] Ship a component library others can adopt
