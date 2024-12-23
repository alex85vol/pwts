# Playwright & TypeScript Framework

This repository contains a test automation framework built with [Playwright](https://playwright.dev/) and [TypeScript](https://www.typescriptlang.org/). The framework is designed for end-to-end testing of web applications.

---

## Features

- **End-to-End Testing**: Write and run tests for web applications using Playwright.
- **TypeScript Support**: Leverage TypeScript's type safety and modern JavaScript features.
- **Cross-Browser Testing**: Test across Chromium, Firefox, and WebKit.
- **Reporting**: Generate detailed HTML reports for test runs.
- **Trace Viewer**: Debug tests with Playwright’s trace viewer.

---

## Prerequisites

- **Node.js** (v16 or later)
- **npm** or **yarn**
- A modern code editor like [VS Code](https://code.visualstudio.com/)

---

## Installation

  1. Clone the repository:
     ```bash
     git clone https://github.com/your-username/your-repo-name.git
     cd your-repo-name
  2. Install dependencies:
      ```bash
      npm install
      ```
## Configuration
Update the playwright.config.ts file for your specific needs. For example, set the browsers, test directory, or base URL.

Example playwright.config.ts:

```
import { defineConfig } from '@playwright/test';

export default defineConfig({
  testDir: './tests',
  timeout: 30000,
  retries: 1,
  reporter: [['html', { open: 'never' }]],
  use: {
    headless: true,
    baseURL: 'https://example.com',
    screenshot: 'on',
    video: 'on',
    trace: 'on-first-retry',
  },
});
```

## Running Tests
   Run all tests:
   ```
    npx playwright test
   ``` 
   
   Run tests in a specific file:
   ```
    npx playwright test tests/example.spec.ts
   ```
  Debug tests:
   ```
    npx playwright test --debug
   ```
## Generate an HTML report:
```
  npx playwright show-report
```
## Folder Structure
```
├── tests/                # Test files
│   ├── example.spec.ts   # Example test file
├── .gitignore            # Ignored files
├── playwright.config.ts  # Playwright configuration
├── package.json          # Project dependencies
├── tsconfig.json         # TypeScript configuration
├── README.md             # Project documentation
```
## Writing Tests
Create test files in the tests/ directory with the .spec.ts extension. Here’s an example:

```
import { test, expect } from '@playwright/test';

test('Example test', async ({ page }) => {
  await page.goto('https://example.com');
  await expect(page).toHaveTitle(/Example Domain/);
  await page.click('text=More information');
  await expect(page).toHaveURL(/iana\.org/);
});
```
## Reporting
After running tests, generate an HTML report with:
```
npx playwright show-report
```
Reports will be stored in the playwright-report/ directory.

## Debugging
Use --debug to run tests in debug mode.
View traces by running:
```
npx playwright show-trace trace.zip
```

## License
This project is licensed under the MIT License.

## Contributions
Feel free to fork this repository and submit pull requests! 😊


This `README.md` provides a clean overview of the framework, how to set it up, and how to use it. You can customize it further to match your project's specifics. Let me know if you'd like any changes! 😊







