---
name: coss-svelte
description: Helps implement coss-svelte UI components correctly. Use when building Svelte or SvelteKit interfaces with coss-svelte primitives, composing Bits UI-backed overlays/forms/menus/selects/tabs/inputs, migrating COSS React, shadcn, or Radix assumptions to Svelte-native code, or checking coss-svelte imports, anatomy, styling, accessibility, and component status boundaries.
compatibility: Requires Svelte 5, SvelteKit for the docs examples, Bits UI peer primitives, and Tailwind CSS 4 theme tokens from coss-svelte.
license: MIT
metadata:
  author: johannhipp
---

# coss-svelte

coss-svelte is a Svelte 5 copy-and-own component library inspired by COSS UI. It maps COSS's compact product UI language onto Svelte-native components, Bits UI behavior, and Tailwind CSS 4 tokens.

## What this skill is for

Use this skill to:

- pick the right coss-svelte primitive for a UI task
- write correct Svelte usage code with documented imports and component parts
- preserve Svelte/Bits UI composition instead of copying React/Base UI APIs
- avoid shadcn, Radix, or COSS React migration mistakes
- respect current component status: stable, experimental, and deferred

## Source of truth

- coss-svelte docs map: `/llms.txt` in the coss-svelte docs app
- component docs: `/docs/components/<slug>.md` in the coss-svelte docs app
- package exports: `packages/coss-svelte/src/index.js`
- component metadata: `packages/coss-svelte/src/metadata.js`
- implementation rules: `coss-svelte/AGENTS.md` and `docs/implementation/*`
- public repo: `https://github.com/johannhipp/coss-svelte`

## Out of scope

- Maintaining COSS React or Base UI source.
- Publishing npm releases unless explicitly requested.
- Inventing component APIs not exported by `coss-svelte`.
- Creating a separate particles skill before coss-svelte has registry-backed Svelte particle manifests.

## Principles for agent output

1. Use documented coss-svelte exports first.
2. Keep code Svelte-native; do not translate React snippets mechanically.
3. Preserve accessibility semantics, labels, control types, focus behavior, and form errors.
4. Prefer compact product UI patterns that match COSS density without adding decorative marketing layout.
5. Check experimental/deferred status before treating a component as production-stable.
6. When adapting COSS React examples, port intent and visual contract, not React/Base UI implementation details.

## Critical usage rules

Always apply before returning coss-svelte code:

- Import components from `coss-svelte`, not from COSS React, shadcn, Radix, or Base UI.
- Do not use React-only patterns such as `asChild`, `render`, hooks, JSX props, `className`, or `onClick={...}` syntax in Svelte output.
- Use Svelte event and binding syntax supported by the target project.
- For overlays and trigger-based components, follow the primitive's documented root/trigger/popup/content hierarchy.
- For forms, keep `Field`, `FieldLabel`, `FieldDescription`, `FieldError`, and inputs grouped semantically.
- For manual install guidance, include `coss-svelte`, `bits-ui`, and the COSS theme import when relevant.

Rule references, read on demand:

- `./references/rules/styling.md` - Tailwind 4 tokens, theme CSS, icons, density, and visual constraints
- `./references/rules/composition.md` - Svelte component composition, overlays, triggers, grouped controls
- `./references/rules/forms.md` - field, form, input, validation, and error display patterns
- `./references/rules/migration.md` - React COSS, shadcn, Radix, and Base UI assumptions to remove

## Component discovery

All scoped components have reference guides at `./references/primitives/<slug>.md`. Start with the registry index:

- `./references/component-registry.md`

## Usage workflow

1. Identify the UI intent: action, form, overlay, selection, feedback, navigation, layout, or display.
2. Read `references/component-registry.md` to choose candidate primitives.
3. Read the primitive reference for each selected component.
4. Read rule references when the task touches forms, overlays, styling, or migration.
5. Generate Svelte code using documented coss-svelte imports and anatomy.
6. Self-check component status, accessibility, and Svelte syntax before returning.

## Installation reference

For app usage:

```bash
pnpm add coss-svelte bits-ui
```

Import the COSS theme once in the app layout:

```svelte
<script>
	import "@coss-svelte/theme/style-coss.css";
</script>
```

For repository development and verification, read `./references/cli.md`.

## High-risk primitives

Read these references before editing related code:

- `./references/primitives/dialog.md` - modal structure, footer actions, forms in dialogs
- `./references/primitives/sheet.md` - side panel semantics and dialog-based composition
- `./references/primitives/drawer.md` - experimental status and deferred parity gaps
- `./references/primitives/select.md` - trigger/value/popup/viewport/item hierarchy
- `./references/primitives/command.md` - command dialog and list composition
- `./references/primitives/form.md` - field semantics and optional validation adapters
- `./references/primitives/sidebar.md` - experimental status and static shell limitations
- `./references/primitives/toast.md` - experimental status and runtime behavior gaps

## Output checklist

Before returning code:

- imports exist in `coss-svelte`
- Svelte syntax is valid
- component anatomy matches the primitive reference
- accessibility labels and explicit control types are present
- status caveats are mentioned for experimental/deferred components
- styling uses coss-svelte theme tokens and existing variants rather than ad hoc one-off classes
