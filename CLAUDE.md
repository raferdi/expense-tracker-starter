# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Starter project for a Claude Code course (codewithmosh.com). A basic React expense/finance tracker. It **intentionally** has a bug, poor UI, and messy code that get fixed over the course — don't "clean up" issues unless asked to; they may be the point of the exercise.

## Commands

```bash
npm install
npm run dev      # start Vite dev server at http://localhost:5173
npm run build    # production build
npm run lint     # eslint
npm run preview  # preview production build
```

There is no test setup in this repo.

## Architecture

Single-page React app scaffolded with Vite (`@vitejs/plugin-react`), no router, no state management library, no backend — everything lives in one component.

- `src/main.jsx` — entry point, mounts `<App />` into `#root`.
- `src/App.jsx` — the entire application: transaction state (`useState`), the add-transaction form, filters (by type/category), summary totals (income/expenses/balance), and the transactions table all live in this one component.
- `src/App.css` — all styling, plain CSS classes matched to `App.jsx` class names (no CSS modules, no Tailwind).

Transactions are plain objects: `{ id, description, amount, type, category, date }`, held in memory only (no persistence — a page refresh resets to the seeded sample data in `App.jsx`).
