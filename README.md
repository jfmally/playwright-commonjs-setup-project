# Playwright JS SDK example — CommonJS with setup project auth

This example illustrates Evinced Playwright JS SDK usage in a CommonJS module
context with authorization in a setup test project.

## Authorization

Evinced SDK requires a Service ID and an API Key when used with Playwright JS.
Licensed users can obtain those from
[Evinced Product Hub - Web SDK](https://hub.evinced.com/web-sdk) and should set
them in their enviornment or in a `.env` file in the project directory before
running tests.

```shell
EVINCED_SERVICE_ID
EVINCED_API_KEY
```

## Installation

A local copy of Evinced SDK must be available as a gzipped tar file. Run NPM or
the package manager of your choice (yarn, pnpm) to install it along with the
other dependencies.

```shell
# Using npm package manager
npm install -D (path to js-playwright-sdk-$version.tgz)
```

## Running the Tests

The example performs two tests across three browsers each. Each test scans
http://demo.evinced.com for accessibility issue using the Evinced engine. (It
should find some.)

- A single-run test using `evAnalyze()`
- A continuous-run test using `evStart()` and `evStop()`

Use either the package manager or `npx` directly to run the tests.

```shell
# Using NPM
npm start

# Using npx
npx playwright test
```

Successful execution should echo the following:

```
> playwright test

Running 7 tests using 5 workers
[auth] › auth.setup.js:4:1 › Authorize Evinced SDK
Evinced SDK authorized.

  7 passed (6.5s)

To open last HTML report run:

  npx playwright show-report
```

Evinced accessibility reports in HTML format should be generated for each test:

- `./test-results/single.html`
- `./test-results/continuous.html`
