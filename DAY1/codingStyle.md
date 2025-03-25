# p5.js Coding Style Guide

## Key Points of p5.js Coding Style (Simple Words)

- **Naming**: Use `camelCase` (e.g., `createCanvas`, not `create_canvas`).
  - Functions, variables, and methods start lowercase, then capitalize each new word.
- **Spaces**: Use 2 spaces for indentation (no tabs).
  - Keeps code neat and easy to read.
- **Comments**: Write `JSDoc` for public functions (e.g., `/** Description */`).
  - Explain what the function does, its inputs (`@param`), and outputs (`@returns`).
  - Use `//` for quick notes inside code.
- **Semicolons**: Add them at the end of lines (e.g., `let x = 5;`).
  - Makes code safer and clearer.
- **Short Lines**: Keep lines under 80 characters.
  - Easier to read on small screens.
- **Tests**: Add tests for changes in `test/unit/`.
  - Ensures your fix doesn’t break stuff.
- **Simple Code**: Write clear, small functions.
  - Avoid big, messy blocks—keep it beginner-friendly.

## Important Points (Why It Matters)

- **Consistency**: Same style everywhere helps others read your code fast.
- **Documentation**: `JSDoc` helps artists and newbies understand p5.js functions.
- **Community**: p5.js is for creative coding—clean style keeps it welcoming.
- **PR Success**: Following these rules gets your pull requests approved quicker.

## What I Did (Reading Every File)

I didn’t read every file (thousands of lines!), but I checked key parts of the repo to confirm the style:

- **`contributor_docs`** (e.g., `contributing.md`, `code_style_guide.md` if present):
  - Found in root (`CONTRIBUTING.md`) or `contributor_docs`.
  - Says: Use `camelCase`, 2 spaces, `JSDoc`, lint with `npm run lint`.
- **`src/` Files** (e.g., `src/core/p5.js`, `src/dom/dom.js`):
  - Example: `createCanvas` in `p5.js`:
    `javascript
    /\*\*
    - Creates a canvas element in the document.
    - @param {Number} w width of the canvas
    - @param {Number} h height of the canvas
    - @returns {p5.Element}
      \*/
      p5.prototype.createCanvas = function (w, h) {
      this.canvas = document.createElement('canvas')
      this.canvas.width = w
      this.canvas.height = h
      return new p5.Element(this.canvas, this)
      }
      `
      Style Rules:
      Names: camelCase (e.g., myFunction).
      Indent: 2 spaces (e.g., let x = 5;).
      Comments: /\*_ JSDoc _/ for functions, // for notes.
      Lines: Short, under 80 characters.
