# Playwright Beginner

This repository contains a Playwright test automation project for learning and practicing end-to-end testing with Playwright Test.

## Project Status

- ✅ Local repository initialized and pushed to GitHub
- ✅ `tsconfig.json` added for TypeScript support
- ✅ Playwright configuration configured for Chromium, Firefox, WebKit, CI, and local projects
- ✅ Sample test files and page object files included
- ✅ GitHub Actions workflow included to run Playwright tests on push and pull requests

## Repository Structure

- `tests/` - main Playwright test files for local practice
- `tests-examples/` - additional example tests
- `pages/` - page object model files for reusable page actions
- `utils/` - utility files such as environment base URLs
- `.github/workflows/playwright.yml` - CI workflow to run Playwright tests on GitHub Actions
- `playwright.config.ts` - Playwright test configuration
- `tsconfig.json` - TypeScript configuration for Node and Playwright
- `package.json` / `package-lock.json` - project dependencies and scripts

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/TufyalAhmmed/plywrightBeginner.git
   cd plywrightBeginner
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Install Playwright browsers:
   ```bash
   npx playwright install
   ```

## Run Tests

- Run the main test suite:
  ```bash
  npm run test:e2e
  ```
- Run all browsers and tests:
  ```bash
  npm run test:e2e:all
  ```
- Run tests in headed mode for development:
  ```bash
  npm run test:e2e:dev
  ```
- Run smoke tests:
  ```bash
  npm run test:e2e:smoke
  ```
- Run non-smoke tests:
  ```bash
  npm run test:e2e:non-smoke
  ```

## Visual (Applitools) Tests

This project includes example visual tests using Applitools Eyes.

Steps to run visual tests:

1. Copy the example env file to create a local `.env` and add your real API key (do NOT commit `.env`):
   ```bash
   cp .env.example .env
   # then edit .env and set APPLITOOLS_API_KEY to your key
   ```
2. Ensure `.env` contains a valid key (no `<` or `>` around the value):
   ```dotenv
   APPLITOOLS_API_KEY=your_real_applitools_api_key_here
   ```
3. Run the visual test example for ACME (Chromium):
   ```bash
   npm run test:visual:acme
   ```

Notes:
- The test file `tests/example-applitools.spec.ts` validates `process.env.APPLITOOLS_API_KEY` at startup and will fail fast if the key is missing.
- Keep secrets out of source control. `.env` is ignored by `.gitignore`.

## Configuration

- `playwright.config.ts` enables parallel execution and retries.
- Shared test options include trace collection on first retry and screenshots on failure.
- Projects are configured for `chromium`, `firefox`, `webkit`, and environment-specific targets like `local` and `ci`.
- Environment variables are loaded using `dotenv` in `playwright.config.ts`.

## GitHub Actions

The workflow `.github/workflows/playwright.yml` runs on `push` and `pull_request` events for `main` and `master` branches. It:

1. Checks out the repository
2. Sets up Node.js
3. Installs dependencies
4. Installs Playwright browsers
5. Runs `npx playwright test`
6. Uploads the generated `playwright-report/` artifact

## Notes

- Update `utils/environmentBaseUrl.ts` with real service URLs as needed.
- Add any environment variables required for CI or local testing in a `.env` file (use `.env.example` as a template).
- `playwright-report/` is excluded in `.gitignore` to avoid committing generated reports.

## Contributing

- Open a PR with a descriptive title. Run tests locally before submitting.
- For documentation fixes, use commit message prefix `docs:`; for functional changes, use `feat:` or `fix:`.

## Commit message suggestion for this change

- `docs(readme): add Applitools usage, .env template, and visual test instructions`

---
Updated on: 2026-08-08
