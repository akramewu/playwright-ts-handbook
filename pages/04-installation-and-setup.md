_Playwright | Automation Testing Handbook 01_

# 2. Installation and Setup

## What you need first

- Node.js version 18 or higher (use the LTS version)
- VS Code (best editor) and optional Git
- Internet, because it downloads the browsers (about 500 MB)

## Steps

① Check Node and npm. Both must show a version number.

```ts
node -v
npm -v
```

② Make a new folder and go inside it.

```ts
mkdir pw-demo
cd pw-demo
```

③ Run the setup command and answer the questions.

```ts
npm init playwright@latest
```

  - Language: TypeScript. Test folder: tests
  - Add GitHub Actions file? Yes. Install browsers? Yes

④ Open the project in VS Code with: code .

## Folder structure after setup

```ts
pw-demo/
  tests/                 // your test files live here
  tests-examples/        // demo tests to learn from
  playwright.config.ts   // all settings in one file
  package.json           // project and scripts
  playwright-report/     // HTML report (after a run)
  test-results/          // screenshots, videos, traces
```

> **Fix common error**
> Error "Executable does not exist"? Browsers are missing. Run: npx playwright install. On Linux CI use: npx playwright install --with-deps

☆ Update later: npm i -D @playwright/test@latest

## VS Code tips

- Install the extension Playwright Test for VS Code
- Green play button beside each test: run it with one click
- Tick Show browser to watch the test run
- Use Record new to create a test by clicking on the website

```ts
// package.json (scripts you can add)
"scripts": { "test": "npx playwright test", "report": "npx playwright show-report" }
```

- 4 -
