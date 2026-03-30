---
name: code-decoded
description: Turns any codebase into a self-contained interactive HTML course. Use when asked to explain a codebase, generate onboarding material, create an interactive tour of a repo, teach how code works, or produce a visual walkthrough for developers or non-technical users. Output is a single HTML file with no dependencies that can be hosted as a landing page or shared directly. Works for any language, any audience level.
---

# Code Decoded

Turn a codebase into a self-contained interactive HTML course. One file. No setup. Host it, share it, or open it locally.

Read `references/html-structure.md` for the HTML output spec.
Read `references/design-principles.md` for visual and content rules.

## What to Build

A single HTML file that teaches how the codebase works through:

- **Scroll-based modules** — one concept per section, progress indicator
- **Code + plain English side by side** — real code from the repo on the left, what it means on the right. Never modify or simplify the code.
- **Architecture overview** — visual diagram of how the main components connect
- **Data flow walkthrough** — trace what happens during a key user action (login, submit, search — whatever is most representative)
- **Interactive quizzes** — application-focused, not memorization. "A user reports stale data after switching pages. Where would you look first?" Not "What does API stand for?"
- **Glossary tooltips** — hover any technical term for a plain-English definition
- **Keyboard navigation** — arrow keys to move between sections

## Before Starting

Ask the user (or infer from context):
1. **Audience** — non-technical (product users, stakeholders), developer onboarding, or power users?
2. **Focus** — full codebase tour, or a specific area (auth, data layer, a specific feature)?
3. **Key action to trace** — what is the most important thing the code does? This becomes the data flow module.

If the user says "just do it" — infer from the codebase and proceed.

## How to Generate

1. Read the codebase structure (directory tree, key files)
2. Identify: entry points, main modules, data models, key user flows
3. Pick 5-8 concepts to teach — ordered from "what is this?" to "how does it work?" to "how do I use/change it?"
4. Write the HTML course following `references/html-structure.md` and `references/design-principles.md`
5. Output as a single `.html` file

## Output

Name the file: `[repo-name]-tour.html`

It must:
- Work offline (no external CDN, no network requests)
- Be self-contained (all CSS and JS inline)
- Render correctly in Chrome, Firefox, Safari
- Be hostable as a static page with no build step
