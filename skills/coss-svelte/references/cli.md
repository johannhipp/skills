# CLI, installation, and repository workflow

## Install this skill

Install only coss-svelte knowledge:

```bash
npx skills@latest add johannhipp/skills --skill coss-svelte
```

List the repository without installing:

```bash
npx skills@latest add johannhipp/skills --list
```

Use `--agent codex --copy -y` for an isolated noninteractive verification install.

## Choose a component consumption path

### Existing consumer

If `coss-svelte` is already in `package.json`, use its installed version. Inspect its generated declarations instead of assuming the latest repository API.

### coss-svelte monorepo

Use workspace packages and the existing lockfile:

```bash
pnpm install --frozen-lockfile
pnpm package:prepare
pnpm check
```

Import components from `coss-svelte` in workspace consumers. Import the workspace theme from `@coss-svelte/theme/style-coss.css` only where the monorepo already wires that package.

### New external consumer

Start from a Svelte 5 application using SvelteKit and Vite. Install both synchronized `0.1.x` packages and the Bits UI peer with the consumer's package manager. The canonical pnpm command is:

```bash
pnpm add coss-svelte @coss-svelte/theme bits-ui
```

Import Tailwind CSS 4 first and the coss-svelte theme second from the global stylesheet loaded by the application layout:

```css
@import "tailwindcss";
@import "@coss-svelte/theme/style-coss.css";
```

Use matching `0.1.x` versions of `coss-svelte` and `@coss-svelte/theme`. Re-read the installed declarations and published peer dependencies when a consumer is pinned to a different release.

## Registry artifacts

- Inspect hosted component manifests at `https://coss-svelte.vercel.app/r/<slug>.json` and the index at `https://coss-svelte.vercel.app/r/index.json`.
- In a source checkout, the same generated artifacts live under `apps/registry/static/r/`.
- Treat the registry as a preview: copy every listed file into the target application, install every listed dependency, and maintain the copied source locally. Registry source and schemas may change between minor releases.
- Do not invent `@coss-svelte/*` shadcn aliases or an alternative registry domain.
- Include every file, external dependency, CSS requirement, and registry dependency recorded by the manifest when manually vending a component.

## Repository checks

Run the narrowest relevant checks from the coss-svelte root:

```bash
pnpm biome:ci
pnpm check
pnpm test
```

For docs or registry work, add the relevant consumer checks:

```bash
pnpm --filter @coss-svelte/www build
pnpm registry:check
pnpm examples:check
```

For publish-facing changes, run:

```bash
pnpm release:check
```

Keep component implementation under `packages/coss-svelte`, generated registry output under `apps/registry`, and docs-only code under `apps/www`.
