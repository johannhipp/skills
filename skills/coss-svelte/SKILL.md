---
name: coss-svelte
description: Implement and troubleshoot coss-svelte interfaces in Svelte 5 or SvelteKit. Use when selecting coss-svelte components, composing Bits UI-backed dialogs, menus, selects, comboboxes, forms, tabs, inputs, or feedback surfaces, adapting COSS React particles or shadcn/Radix code to Svelte, or verifying imports, bindings, status, registry artifacts, theme setup, accessibility, and install availability.
---

# coss-svelte

Implement COSS-shaped product UI with Svelte 5 components, Bits UI behavior, and the coss-svelte visual contract. Port interaction and visual intent from COSS React; never port its implementation source.

## Establish the source contract

Resolve disagreements in this order:

1. `packages/coss-svelte/src/index.js` and generated `dist/index.d.ts` for public exports.
2. Generated component declarations and `src/components/*.svelte` for props, bindings, snippets, and behavior.
3. `packages/coss-svelte/src/metadata.js` for status, foundation, parts, and upstream particle counts.
4. `apps/registry/static/r/*.json` for copy-and-own file closure and dependencies.
5. The docs app and `/docs/components/<slug>.md` routes for discovery, not as a substitute for declarations.

Use <https://github.com/johannhipp/coss-svelte> when the source repository is not local. Treat <https://coss.com/ui/> and its particles as React design references only.

## Apply the component model

- Prefer a root component's convenience props (`items`, `options`, `tabs`, `title`, `description`) for simple flows.
- Compose exported child parts when custom structure, actions, or rich content is required.
- Read the primitive guide before mixing the two modes. Children replace fallback markup for many roots; `Dialog`, `AlertDialog`, `Sheet`, and `Drawer` instead activate convenience scaffolds when root `title` or `description` is set.
- Use Svelte 5 syntax: `class`, lowercase property events such as `onclick`/`onsubmit`, `$state`, snippets, and documented `bind:*` contracts.
- Use callback props such as `onValueChange` only where declarations expose them.

## Critical rules

- Import only names exported by `coss-svelte`. Never invent parity APIs.
- Never use React/JSX, hooks, `className`, `onClick`, Base UI, Radix `asChild`, or COSS `render` composition in Svelte output.
- Never import `NumberField` while metadata marks it deferred; it is not exported.
- Mark Drawer, Sidebar, and Toast as experimental and describe their current limitations.
- Do not describe the upstream count of 484 COSS particles as installable Svelte particles. Use [the pattern index](./references/particles.md) to discover intent, then port it.
- Preserve labels, dialog titles/descriptions, roles, focus behavior, keyboard behavior, error semantics, and explicit button/input types.
- Verify package availability before giving external install commands. The source baseline may be ahead of npm and the theme package may still be workspace-only.

## Workflow

1. Determine whether the task is inside the coss-svelte monorepo, in an existing consumer, or for a new external install.
2. Read [the component registry](./references/component-registry.md) and select the smallest suitable stable surface.
3. Read every selected primitive guide under `references/primitives/`.
4. Read the relevant rule guide for composition, forms, styling, or migration.
5. For production-like patterns, search [the upstream particle index](./references/particles.md), then translate it through current Svelte exports.
6. Implement the minimal accessible Svelte pattern.
7. Check imports, status, value shapes, bindings, and source availability before returning code.

## Reference routing

- [CLI and availability](./references/cli.md) — skill install, package/registry availability, monorepo checks
- [Component registry](./references/component-registry.md) — all 54 components grouped by purpose and status
- [Composition](./references/rules/composition.md) — convenience vs composed roots, overlays, bindings, snippets, providers
- [Forms](./references/rules/forms.md) — Field context, native Form behavior, validation, input bindings
- [Styling](./references/rules/styling.md) — theme availability, tokens, variants, `cn-*`, Tailwind CSS 4
- [Migration](./references/rules/migration.md) — React COSS/Base UI/shadcn/Radix/particle conversion
- [Particle patterns](./references/particles.md) — 484 searchable upstream pattern descriptions with strict porting boundaries

## Read these guides first for risky work

- [Dialog](./references/primitives/dialog.md), [Alert Dialog](./references/primitives/alert-dialog.md), [Sheet](./references/primitives/sheet.md), and [Drawer](./references/primitives/drawer.md) for modal structure and form placement
- [Menu](./references/primitives/menu.md), [Select](./references/primitives/select.md), [Combobox](./references/primitives/combobox.md), and [Autocomplete](./references/primitives/autocomplete.md) for collection and popup contracts
- [Field](./references/primitives/field.md), [Form](./references/primitives/form.md), and [Input Group](./references/primitives/input-group.md) for accessible form wiring
- [Command](./references/primitives/command.md) for command-dialog anatomy
- [Sidebar](./references/primitives/sidebar.md) and [Toast](./references/primitives/toast.md) for experimental boundaries

## Installation

Install this agent skill with:

```bash
npx skills@latest add johannhipp/skills --skill coss-svelte
```

Read [CLI and availability](./references/cli.md) before suggesting component-package or theme installation.

## Final check

- Confirm every import exists in the current package.
- Confirm every binding and callback appears in generated declarations.
- Confirm scalar versus array value shapes match single versus multiple mode.
- Confirm composed overlays contain their required trigger, popup, title/description, body, footer, and close/action parts.
- Confirm forms keep submit controls inside the form and propagate invalid/required/disabled state through Field.
- Confirm experimental and deferred caveats are explicit.
- Confirm React particles were reimplemented, not copied.
