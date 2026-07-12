# Azure DevOps Test Case Manager — V2 (Releases)

Installer and **auto-update feed** for Test Case Manager V2, a Windows desktop
app for authoring, importing, editing, and **running** Azure DevOps test cases
against a Product Backlog Item — plus a lightweight Work Manager for triaging
your work items. Built with Tauri 2 + Rust + React/TypeScript.

This repository holds only the packaged releases. **Source code is in the
private repository.**

## Install

1. Download **`AzureDevOpsTestCaseManager.V2-win-Setup.exe`** from the
   [latest release](../../releases/latest).
2. Run it. The app installs per-user and launches itself.
3. Sign in with your Microsoft account when prompted.

There's also a **`-win-Portable.zip`** if you prefer an unpacked build. After
the first install the app **updates itself** from this feed on launch — you
don't need to download future versions manually.

## What it does

- **Manual Entry** — author test cases (steps grid, module picklist, tags).
- **Import File** — JSON round-trip import/export; a kept id updates, a null id
  creates.
- **Edit Test Cases** — multi-select (ctrl/shift), bulk edit, group by title.
- **Run Tests & Runner** — record outcomes inline or in an always-on-top runner
  with per-step results, screenshots (snip / paste / attach), and bug filing;
  submits a new test run under the PBI's plan.
- **Test Suites** — a searchable multi-level folder tree with view/edit/run.
- **Work Manager** — a To Do / In Progress / Done board with a detail drawer
  (markdown descriptions, comments, quick-create).
- **Themes** — selectable full-UI palettes (Light, Slate, Midnight, Graphite,
  Ocean, OLED) with accent presets.

## Safety

- **No DELETE calls, anywhere** — the app never deletes work items, cases,
  runs, or attachments.
- **Token in memory only** — your Microsoft access token is never written to
  disk or logged, and never leaves the app's Rust core.
- **Confirm before writes** — reads happen freely; creates/updates are gated by
  a review step.

## Authentication

Interactive Microsoft sign-in (MSAL / PKCE) through your browser using the
well-known Azure CLI public client — no Personal Access Token or app
registration required.
