_Playwright | Automation Testing Handbook 01_

# 1. What is Playwright?

Playwright is a free, open-source tool to test web apps. It was made by Microsoft and released in 2020. It controls a real browser using code.

- Browsers: Chromium (Chrome, Edge), Firefox and WebKit (Safari)
- Languages: JavaScript / TypeScript, Python, Java and .NET (C#)
- Runs on Windows, Mac and Linux, and also in CI/CD servers
- Tests: web UI, REST APIs, mobile web (emulation) and components

## Why do testers love it?

- [x] Auto-wait: it waits for elements by itself. No more sleep()
- [x] Very fast: tests run in parallel by default
- [x] One API for all browsers. Write once, run on 3 engines
- [x] Free tools inside: Codegen, Trace Viewer, UI Mode, HTML report
- [x] Every test gets a fresh and isolated browser context

## Playwright vs Selenium

| Feature | Selenium | Playwright |
|---|---|---|
| Waiting | Manual waits | Auto-wait built in |
| Setup | Drivers needed | One command |
| Speed | Slower | Faster |
| Parallel run | Grid / TestNG | Built in |
| Debug tools | Basic | Trace Viewer, UI Mode |
| Browsers | Many, even old | Chromium, Firefox, WebKit |
| Languages | Many | JS/TS, Python, Java, C# |

## How it talks to the browser

```
Test script  -->  Playwright library  -->  Browser  -->  Web app
```

> **Interview tip**
> Playwright keeps one fast WebSocket connection to the browser. Classic Selenium sends many HTTP requests. This is one reason why Playwright is faster.

## Words you must know

- Locator: a way to find an element on the page
- Fixture: ready object given to a test (page, context, request)
- Browser context: a fresh, isolated browser profile (like incognito)
- Headless: browser runs without a visible window. Faster for CI
- Spec file: a file that has your tests, like login.spec.ts
- Project: one browser or device setup in the config file

- 3 -
