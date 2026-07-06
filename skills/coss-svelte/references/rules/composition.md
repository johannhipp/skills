# Composition Rules

- Compose with Svelte components and slots; do not use React-only `asChild`, `render`, hooks, JSX children, or `className` syntax.
- Trigger-based components should keep root, trigger, popup/content, title/description, body/panel, and footer parts in the documented order.
- Dialog-like components should separate header, panel/content, and footer when those parts exist.
- Selection components should keep trigger/value separate from popup/viewport/item parts.
- Command and autocomplete components depend on their list/collection/item hierarchy; do not flatten them into plain divs when the primitive exposes parts.
- Native presentational components can use semantic HTML directly, but keep exported coss-svelte parts when docs list them.
- For experimental components, prefer docs examples and mention limitations instead of promising full upstream COSS parity.
