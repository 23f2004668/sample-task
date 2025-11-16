# Test App — Developer Toolbox

## Overview
A single-page, zero-dependency web app that helps you quickly test:
- JavaScript snippets in a safe, sandboxed environment (with async/await and console capture)
- Regular expressions with live highlighting and match details
- HTTP requests with custom headers, body, timeout, and pretty-printed responses

It’s designed to be fast, local-first, and convenient for everyday developer tasks.

## Setup
- Download index.html
- Open index.html in any modern browser (Chrome, Edge, Firefox, Safari)

Optional:
- For HTTP testing against some APIs, CORS may block requests if opened via file://. If needed, serve the file locally:
  - Python: python3 -m http.server 8080
  - Node: npx serve
  - Then open http://localhost:8080

## Usage

### JS Runner
- Write JavaScript in the editor. Top-level await is supported.
- Click “Run” (or press Ctrl/Cmd + Enter) to execute in a sandboxed iframe without DOM/network access.
- View captured console logs, execution time, result, and errors.
- Adjust timeout (ms) to limit long-running code.

Example:
- console.log('Hi'); await Promise.resolve(42); 40 + 2

### Regex Tester
- Enter a pattern and toggle flags (g, i, m, s, u, y).
- Type or paste a test string to see live match highlighting.
- The “Matches” panel lists each match with index and captured groups.
- Use “Load Sample” for a quick demo.
- Your last pattern, flags, and text are saved automatically.

### HTTP Tester
- Choose method and enter a URL (example seeded: https://jsonplaceholder.typicode.com/todos/1).
- Add headers as needed; Accept: application/json is added by default.
- Optionally enter a request body (raw text). Use “Pretty JSON” or “Minify JSON” utilities.
- Set a timeout (ms) and click “Send” (or Ctrl/Cmd + Enter).
- See status, timing, size, response headers, and pretty-printed response body.
- Notes:
  - CORS may limit requests from local files; serve locally if necessary.
  - For JSON bodies, set Content-Type: application/json. The app will auto-set this when body begins with { if not already specified.

Enjoy quick testing across JS, regex, and HTTP in one minimal tool.