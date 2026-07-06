# CLI and Repository Workflow

## App install

```bash
pnpm add coss-svelte bits-ui
```

Import the theme once in the Svelte app layout:

```svelte
<script>
	import "@coss-svelte/theme/style-coss.css";
</script>
```

## Local development

From the coss-svelte repo root:

```bash
pnpm install --frozen-lockfile
pnpm biome:ci
pnpm check
pnpm test
```

For docs routes specifically:

```bash
pnpm --filter @coss-svelte/www build
```

## Source boundaries

- Component source lives in `packages/coss-svelte/src/components`.
- Public exports live in `packages/coss-svelte/src/index.js`.
- Component metadata lives in `packages/coss-svelte/src/metadata.js`.
- Docs app routes live in `apps/www/src/routes`.
- Do not copy COSS React or Base UI implementation source into Svelte files.
