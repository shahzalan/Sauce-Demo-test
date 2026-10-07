# SauceDemo Playwright Automation

This project contains Playwright end-to-end tests for the public SauceDemo demo site.

## Prerequisites

- Node.js 20+
- npm
- Chromium browser support for Playwright

## Install

```powershell
npm.cmd ci
npx.cmd playwright install chromium
```

## Run tests

Set the demo credentials in the current PowerShell session:

```powershell
$env:SAUCEDEMO_USERNAME = "standard_user"
$env:SAUCEDEMO_PASSWORD = "secret_sauce"
npm.cmd test
```

To run a specific test by name:

```powershell
npm.cmd test -- -g "standard user completes checkout with the Backpack and Bike Light"
```

## Project files

- `playwright.config.ts` — Playwright config with Chromium and failure artifacts
- `tests/homepage.spec.ts` — SauceDemo login, cart, and checkout scenarios
- `playwright-report/` — generated HTML report output

## Notes

- The tests read credentials from environment variables instead of storing them in source files.
- The live SauceDemo demo UI is used for validation; this verifies the browser flow only, not a real payment or backend order.
