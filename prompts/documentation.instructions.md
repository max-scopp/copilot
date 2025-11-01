---
applyTo: '**/*.{md,mdx}'
description: Instruction template for creating high-quality user-facing documentation for tools and libraries. Focuses on clarity, structure, and usefulness for real users rather than internal developers.
---

# User-Facing Documentation Instruction

## Purpose
Provide clear, actionable guidance for writing user-facing documentation that helps people understand, use, and succeed with your tool or library. This is for end-users — not internal developers or contributors — and focuses on clarity, structure, and empathy over technical detail.

## Rules
- Write for a **skilled but unfamiliar** audience — they know the domain but not your tool.
- Use **task-oriented** language: describe what users can *do*, not just what exists.
- Prefer **examples before explanations**; users learn by doing.
- Keep **each page focused**: one intent, one main goal.
- Avoid filler like “simply”, “just”, “basically”, or “obviously”.
- Use **consistent terminology** and link to concepts rather than redefining them.
- Each heading should **promise an outcome**, not a concept (“Connect to your database”, not “Database connection”).
- Use **second person (“you”)** to keep the tone direct and instructional.
- Support visual learners: use screenshots, code examples, or diagrams where they clarify.
- Never mix tutorial, guide, and reference content in one file — structure them distinctly.

## Best Practices
- Follow the [Diátaxis](https://diataxis.fr/) framework:
  1. **Tutorials** – step-by-step learning by doing.
  2. **How-to guides** – concrete instructions for common goals.
  3. **Reference** – factual, complete API/configuration data.
  4. **Explanation** – background, concepts, rationale.
- Keep sections modular and link between them for user flow.
- Ensure every example is **copy-paste runnable** and demonstrates real use.
- Write **for scanning**: short sentences, bullet lists, and informative headings.
- Use consistent tone and formatting across all docs.
- Update content regularly and remove obsolete examples or links.

## Examples
### ✅ Good
> **Connect your app**
>
> To connect your app to the API:
> 1. Generate an access token.
> 2. Add it to your `.env` file.
> 3. Run `mytool connect`.
>
> You’re now authenticated — continue with [Sending your first request](./sending-your-first-request.md).

### ❌ Bad
> The API connection uses OAuth2. You can use the CLI to connect. Just type the command and it should work.

## References
- [Diátaxis Documentation Framework](https://diataxis.fr/)
- [How to Use Diátaxis](https://diataxis.fr/how-to-use-diataxis/)
- [Dask: Documentation Framework Adoption](https://blog.dask.org/2022/07/15/documentation-framework)
- [Diátaxis for Complex Hierarchies](https://diataxis.fr/complex-hierarchies/)
- [Write the Docs Community](https://www.writethedocs.org/)
- [Google Developer Documentation Style Guide](https://developers.google.com/style)
- [Jacob Kaplan-Moss: Docs for Humans](https://jacobian.org/2017/may/16/docs-for-humans/)
- [Daniele Procida: What nobody tells you about documentation](https://speakerdeck.com/evildmp/what-nobody-tells-you-about-documentation)
- [Divio Blog – How to structure documentation](https://www.divio.com/blog/documentation/)