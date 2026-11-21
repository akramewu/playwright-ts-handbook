# Playwright + TypeScript Handbook

**[📖 Open the handbook (PDF)](Playwright-Handbook-01.pdf)**

Handwritten notes on Playwright automation testing with TypeScript — beginner to advanced.

## Practice setup

[`pw-demo/`](pw-demo) — a ready-to-run Playwright + TypeScript project, scaffolded exactly as described on page 4 of the handbook (TypeScript, `tests` folder, GitHub Actions), using **pnpm** as the package manager.

```bash
cd pw-demo
pnpm install
pnpm exec playwright install
pnpm test
```

Any new package goes in the same way — `pnpm add -D <package>` instead of `npm install -D`, and one-off CLIs run via `pnpm dlx <package>` instead of `npx <package>`.

## What's inside

- Install Playwright and write your first test
- Locators, actions and assertions
- Auto-waiting, hooks, tags and Page Object Model
- Frames, tabs, downloads and API testing
- Config, parallel run, debugging and reports
- CI/CD with GitHub Actions + interview questions

Subject: Automation Testing | Topic: Playwright | 19 pages
