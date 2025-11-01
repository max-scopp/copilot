---
applyTo: '**/*'
description: Instruction template for writing and maintaining documentation using Starlight and Astro. Focuses on using built-in components, MDX features, and layout conventions effectively.
---

# Starlight & Astro Documentation Instruction

## Purpose
Define clear and consistent practices for authoring documentation in **Starlight** (Astro’s official documentation theme). This ensures writers use the right components, imports, and Markdown/MDX patterns to produce accessible, professional, and uniform documentation.

## Rules
* Use **MDX** (`.mdx`) files when embedding any JSX components or dynamic content.
* Always **import Astro/Starlight components** explicitly when used — do not assume global availability:
```mdx
import { Aside } from '@astrojs/starlight/components';
```
* Use **Markdown for prose**, **components for structure**, and **fenced code blocks** for examples.
* Each page must include frontmatter with a `title` and (if applicable) `description`:

  ```yaml
  ---
  title: "Getting Started"
  description: "Set up and run your project with Starlight."
  ---
  ```
* Keep a logical **hierarchy of headings** (`#`, `##`, `###`) — no skipped levels.
* Avoid raw HTML unless Astro components can’t achieve the same result.
* Wrap content sections with appropriate components (e.g., `<CardGrid>`, `<Tabs>`, `<Aside>`).
* Use `<Aside>` only for **contextual notes** — not for main content.
* For code samples:

  * Use ` ```js`, ` ```ts`, etc. fenced blocks.
  * Prefer short, focused snippets that demonstrate one concept.
* Never inline long code blocks inside `<Aside>` or `<Callout>` — link or reference instead.

## Best Practices

* **Structure** content consistently:

  1. Intro paragraph – what the reader will achieve.
  2. Step-by-step or conceptual content.
  3. Optional: `<Aside>` for extra context or pitfalls.
  4. Summary or “Next steps” section.
* **Import only what’s used**; avoid unnecessary imports from `@astrojs/starlight/components`.
* Use **Astro components for visual layout**, not Markdown hacks.
* Prefer **semantic components** like `<Card>`, `<Table>`, `<Callout>` instead of raw `<div>`s.
* Keep **non-interactive content static**; avoid JS-heavy widgets unless required.
* Use **`starlight:sidebar`** for navigation configuration instead of hard-coded links.
* For tabbed examples:

```mdx
import { Tabs, TabItem } from '@astrojs/starlight/components';

<Tabs>
  <TabItem label="JavaScript">
    ```js
    console.log('Hello');
    ```
  </TabItem>
  <TabItem label="TypeScript">
    ```ts
    console.log('Hello');
    ```
  </TabItem>
</Tabs>
```
  
## Multiple Options and Tabs

- **Use `<Tabs>` whenever multiple methods or tools exist** for achieving the same goal (e.g., installation commands, framework-specific instructions, language variants).  
- Each tab should represent **one clear alternative** (e.g., `npm`, `pnpm`, `bun`, `yarn`).  
- Always **import the Tabs components** before using them:

```mdx
import { Tabs, TabItem } from '@astrojs/starlight/components';
```

* Use the **same storage key** across pages where applicable so the user’s selected tab persists across the documentation session:

```mdx
<Tabs storageKey="install-tool">
  <TabItem label="npm">
    ```bash
    npm install mypackage
    ```
  </TabItem>
  <TabItem label="pnpm">
    ```bash
    pnpm add mypackage
    ```
  </TabItem>
  <TabItem label="yarn">
    ```bash
    yarn add mypackage
    ```
  </TabItem>
  <TabItem label="bun">
    ```bash
    bun add mypackage
    ```
  </TabItem>
</Tabs>
```

* **Rules for tabs usage:**

  * Never combine multiple tools in a single code block.
  * Label tabs clearly and concisely.
  * Include only relevant commands for the context.
  * Keep examples short and focused on one concept per tab.
  * Use storage keys to **persist user preferences**, improving the UX when switching pages.

## Examples

### ✅ Good

````mdx
import { Aside } from '@astrojs/starlight/components';

# Installing Starlight

Run the following command to create a new documentation project:

```bash
npm create astro@latest -- --template starlight
```

<Aside type="tip">
You can also use `pnpm` or `yarn` if preferred.
</Aside>
````

### ❌ Bad

```mdx
# Installing Starlight
<aside>Note: You can also use yarn</aside>
```

## References

* [Starlight Documentation](https://starlight.astro.build/)
* [Astro Documentation](https://docs.astro.build/)
* [Astro Components Reference](https://docs.astro.build/en/reference/api-reference/)
* [Starlight Components API](https://starlight.astro.build/reference/components/)
* [Astro MDX Integration](https://docs.astro.build/en/guides/integrations-guide/mdx/)
* [Starlight Customization Guide](https://starlight.astro.build/guides/customization/)
* [Diátaxis Framework](https://diataxis.fr/)
