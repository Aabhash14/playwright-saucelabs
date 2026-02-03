# Playwright Assignment - SauceDemo

Hi! I am learning Playwright, so this project is a simple practice assignment. I automated login tests for the SauceDemo site and added HTML reporting.

## What I tested
I check all the available users on the login page:
- `standard_user`
- `locked_out_user`
- `problem_user`
- `performance_glitch_user`
- `error_user`
- `visual_user`

Test logic is simple:
- Valid users login successfully and land on the **inventory page**.
- `locked_out_user` cannot login (shows the **Epic sadface** error message because of invalid user details).

## Tech used
- Playwright Test (JavaScript)
- HTML reporter

## Project structure
- `tests/pages/login.page.js` - login page actions and error check
- `tests/pages/inventory.page.js` - inventory page checks
- `tests/testscripts.spec.js` - all login test cases (data-driven)
- `playwright.config.js` - browsers and reporters setup
- `playwright-report/` - Playwright HTML report

## Requirements
- Node.js 18+
- npm

## Setup
```bash
mkdir playwright-saucelabs
cd playwright-saucelabs
npm init -y
npm init playwright@latest
```

## Run tests
Run all tests:
```bash
npx playwright test
```

Run only this file:
```bash
npx playwright test tests/testscripts.spec.js
```

Run in headed mode:
```bash
npx playwright test --headed
```

## Reports
Playwright HTML report:
```bash
npx playwright show-report
```

## Notes
- I used Page Object Model (POM) to reduce duplication.
- Tests are reusable, scalable, and maintainable because page actions are centralized and test data is separated from test logic.
- I used a data-driven approach (user list) to run the same flow for multiple users.
- Tests run on Chromium, Firefox, and WebKit from `playwright.config.js`.

## Troubleshooting
- If tests fail to start, run `npx playwright install` again.


