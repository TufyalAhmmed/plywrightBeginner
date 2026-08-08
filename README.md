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

## Configuration

- `playwright.config.ts` enables parallel execution and retries.
- Shared test options include trace collection on first retry and screenshots on failure.
- Projects are configured for `chromium`, `firefox`, `webkit`, and environment-specific targets like `local` and `ci`.
- Environment variables can be loaded using `dotenv`.

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
- Add any environment variables required for CI or local testing in a `.env` file.
- Add `playwright-report/` to `.gitignore` if you do not want generated reports committed.
