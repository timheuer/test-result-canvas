# Test Result Canvas

A GitHub Copilot canvas app extension for viewing C# test results produced in TRX format.

The extension registers a **Test Results** canvas (`trx-results-viewer`) that scans the current workspace for `.trx` files, parses TRX test run output, and shows a focused test ledger with summary counts, filtering, search, durations, host names, categories, failure messages, stack traces, and captured output.

## Features

- Automatically opens the latest TRX result after `dotnet test` or another test command runs.
- Finds TRX files in the workspace, excluding common generated folders.
- Supports uploading a standalone `.trx` file in the canvas.
- Shows pass/fail/skipped counts, pass rate, and total duration.
- Filters by outcome and searches test names, classes, methods, outcomes, categories, and error text.
- Keeps TRX file access scoped to the current workspace.

## Extension layout

```text
.github/extensions/test-result-viewer/
  extension.mjs
  manifest.json
```

`extension.mjs` is the Copilot extension entrypoint. `manifest.json` describes the canvas app metadata, capabilities, and registered canvas.

## Usage

1. Run C# tests with TRX logging, for example:

   ```powershell
   dotnet test --logger trx
   ```

2. Open the **Test Results** canvas, or let the extension open the latest result automatically after the test command completes.

3. Select a `.trx` file from the workspace dropdown or upload a TRX file directly.

## License

This project is licensed under the MIT License. See [LICENSE.md](LICENSE.md).
