# Styling rules

## Install the theme

Install `@coss-svelte/theme` at the same `0.1.x` version as `coss-svelte`. Import Tailwind CSS 4 before the public theme entry in the application's global stylesheet:

```css
@import "tailwindcss";
@import "@coss-svelte/theme/style-coss.css";
```

- Load that stylesheet once from the application layout/root.
- Keep Tailwind CSS 4 source scanning compatible with copied or installed Svelte component files.
- Preserve semantic variables for background, foreground, border, primary, muted, destructive, info, success, warning, sidebar, radius, typography, and motion.

## Style components

- Prefer component `variant`, `size`, `side`, `orientation`, and state props before adding classes.
- Pass classes with Svelte's `class` prop, never `className`.
- Prefer semantic utilities such as `bg-background`, `text-muted-foreground`, and `border-border` over raw palette values.
- Preserve existing `cn-*` classes and `data-slot` hooks when modifying library components or vendored registry files.
- Use `data-*` state selectors supplied by Bits UI/coss-svelte instead of reimplementing state in custom classes.
- Keep product UI compact and operational; avoid oversized marketing typography, decorative gradients, and gratuitous nested cards.

## Icons and interaction states

- Reuse the target project's icon library. The docs workspace uses `@lucide/svelte`; do not add it when another icon set is already present.
- Mark redundant decorative icons `aria-hidden="true"` and label icon-only buttons.
- Preserve focus-visible, hover, active, disabled, invalid, loading, dark-mode, and reduced-motion behavior.
- Do not replace accessible text with an icon whose meaning is ambiguous.
