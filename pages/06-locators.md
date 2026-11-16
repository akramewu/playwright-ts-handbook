_Playwright | Automation Testing Handbook 01_

# 4. Locators

A locator tells Playwright how to find an element. It is lazy: it searches again and again at the moment of the action, so it never goes stale.

## Which locator first? (best to worst)

| Locator | Example | Use when |
|---|---|---|
| getByRole | getByRole('button', {name:'Login'}) | BEST. Like a real user |
| getByLabel | getByLabel('Email') | Form fields with label |
| getByPlaceholder | getByPlaceholder('Search') | Input hint text |
| getByText | getByText('Welcome') | Visible text |
| getByAltText | getByAltText('logo') | Images |
| getByTestId | getByTestId('submit-btn') | data-testid is stable |
| locator (CSS) | locator('#login') | When others fail |
| locator (XPath) | locator('//div[@id="a"]') | Last choice |

## Smart tricks

```ts
page.locator('.card').getByRole('button')            // chaining
page.getByRole('listitem').filter({ hasText: 'Apple' })
page.getByRole('row').first()    // .last()  .nth(2)
const n = await page.getByRole('link').count();
for (const el of await page.getByRole('link').all()) { ... }
```

- Strict mode: if a locator finds 2 or more elements and you click, Playwright throws an error. Make it more specific or use .first()
- Use data-testid and change its name in config: use: { testIdAttribute: 'data-qa' }

> **Do not do this**
> Never use long XPath like /html/body/div[2]/div[1]/span. It breaks when the page changes. Prefer role, label and text.

## Common roles for getByRole

| Role | Element |
|---|---|
| button | button, input type=submit |
| link | a tag with href |
| heading | h1 to h6 (use level: 2) |
| textbox | text input and textarea |
| checkbox / radio | tick boxes and radio buttons |
| combobox | select dropdown |
| row / cell | table rows and cells |

☆ Find the best locator fast: run codegen, or use Pick locator in VS Code

- Combine: loc.and(other) and loc.or(other) for tricky cases

- 6 -
