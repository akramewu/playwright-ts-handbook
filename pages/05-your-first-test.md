_Playwright | Automation Testing Handbook 01_

# 3. Your First Test

`tests/example.spec.ts`

```ts
import { test, expect } from '@playwright/test';

test('has title', async ({ page }) => {
  await page.goto('https://playwright.dev/');
  await expect(page).toHaveTitle(/Playwright/);
});
```

## Line by line

- import: test and expect come from @playwright/test
- test(name, fn): creates one test case with a name
- async / await: browser work takes time, so we wait for each step
- { page }: a fixture. Playwright gives a fresh page to every test
- page.goto(url): opens the website
- toHaveTitle(/regex/): checks the page title. A regex matches part of it

## Second test: click and check

```ts
test('get started link', async ({ page }) => {
  await page.goto('https://playwright.dev/');
  await page.getByRole('link', { name: 'Get started' }).click();
  await expect(page.getByRole('heading', { name: 'Installation' }))
    .toBeVisible();
});
```

## Run commands

| Command | What it does |
|---|---|
| npx playwright test | Run all tests (headless) |
| ... test --headed | See the browser open |
| ... test login.spec.ts | Run one file only |
| ... test -g "has title" | Run test by name |
| ... test --project=chromium | Run one browser only |
| ... test --ui | Open UI Mode |
| npx playwright show-report | Open HTML report |

> **Remember**
> File names must end with .spec.ts or .test.ts. By default tests run headless and on 3 browsers.

## Headed or headless?

- Headless (default): no window, very fast, best for CI
- Headed: you see the browser. Best when you write or debug a test
- A failed run prints an error and a link to the HTML report

☆ Reports are saved in the playwright-report folder

- 5 -
