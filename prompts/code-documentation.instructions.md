---
applyTo: '**'
description: Enforces concise, practical JSDoc and comment style
---

# Enforce concise, no-@tag JSDoc and minimal comments

## Purpose
Ensure all JSDoc and inline comments are short, direct, and only added when the code cannot explain itself. Prevent verbose or boilerplate JSDoc with `@param`, `@returns`, or similar tags. Promote practical, single-sentence documentation that adds contextual value instead of restating the code.

## Rules
- Do **not** use any `@param`, `@returns`, or similar tags in JSDoc.
- Write JSDoc in **a single concise sentence**, summarizing the purpose clearly.
- Use JSDoc **only** when the code’s intent isn’t obvious from its structure.
- Avoid restating what the code already conveys.
- Use inline `//` comments only for explaining domain background, reasoning, or non-obvious context — not for describing code flow.
- Omit comments entirely if the code is self-explanatory.
- Always use the proper JSDoc block form:
```ts
  /**
   * text
   */
```

Never use inline or malformed block comments such as:

```ts
/* text */   // ❌
/** text */  // ❌
```

## Best Practices
- Favor clarity and brevity over completeness.
- Keep the reader focused on *why* the code exists, not *what* it does.
- Use active, direct language.
- Avoid filler words like “This function” or “This method”.
- When documentation is needed, prefer a single-sentence form that can fit on one line.

## Examples

### ✅ Good
```ts
/**
 * From EventEmitter<T>, extract type T, returns `undefined` if not EventEmitter<T> or missing.
 */
```

```ts
// this counter tracks user session refreshes, not clicks.
```

### ❌ Bad

```ts
/**
 * Extracts the generic type parameter T from EventEmitter<T>.
 * Returns undefined if the type is not EventEmitter<T> or if the generic parameter is not present.
 *
 * @param propertyDeclaration - The property declaration with the EventEmitter type
 * @returns The generic type parameter or undefined
 */
```

```ts
// Increments the counter by one
```

## References

* [JSDoc Style Guide (TypeScript Handbook)](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html)
* [Steve McConnell – *Good Code Is Its Own Best Documentation*](https://www.goodreads.com/quotes/9057917-good-code-is-its-own-best-documentation-as-you-re-about)
* [Joel Spolsky – *How to Be a Programmer*](https://www.arl.wustl.edu/projects/fpx/research/HowToBeAProgrammer.pdf)
* [Software Engineering Education – *Writing Good Documentation*](https://se-education.org/learningresources/contents/projectManagement/documentation.html)