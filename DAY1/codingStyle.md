# p5.js Coding Style Guide (Short & Simple)

## Key Points

- **Names**: Use `camelCase` (e.g., `createCanvas`).
- **Spaces**: 2 spaces, no tabs.
- **Comments**: `/** JSDoc */` for functions, `//` for notes.
- **Semicolons**: Add them (e.g., `let x = 5;`).
- **Lines**: Keep short (under 80 characters).
- **Tests**: Add in `test/unit/`.
- **Functions**: Small, clear, one job each.
- **Errors**: Friendly messages (e.g., `throw 'Oops!'`).
- **Simple**: No tricky JS, keep it easy.

## Why It Matters

- **Consistency**: Easy to read for everyone.
- **Docs**: Helps beginners understand.
- **Community**: Keeps p5.js fun and friendly.
- **PRs**: Gets your fixes approved fast.

## What’s p5.js About?

- **Goal**: Easy coding for artists in the browser.
- **Idea**: Makes drawing and fun stuff simple (e.g., `createCanvas`).
- **Parts**:
  - `src/core/`: Main tools.
  - `src/dom/`: HTML bits.
  - `lib/`: Built files.

## What I Checked

- **`contributor_docs`**: `camelCase`, 2 spaces, `JSDoc`.
- **`src/core/p5.js`**:
  ```javascript
  /** Creates a canvas */
  p5.prototype.createCanvas = function (w, h) {
    this.canvas = document.createElement('canvas')
    this.canvas.width = w
    return new p5.Element(this.canvas, this)
  }
  ```
