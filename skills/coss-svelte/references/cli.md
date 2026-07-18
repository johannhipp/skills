# CLI, availability, and repository workflow

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

Check publication before suggesting installation:

```bash
npm view coss-svelte version
npm view @coss-svelte/theme version
```

If either command returns 404, do not present `pnpm add coss-svelte` or the theme import as working public setup. At the current skill baseline, both packages are versioned `0.0.0` in source and are not published to npm.

After publication is verified, install the package and declared peers with the user's package manager. Re-read the published README and peer dependencies; do not freeze a future command into generated guidance.

## Registry artifacts

- Inspect component manifests at `apps/registry/static/r/<slug>.json`.
- Inspect the index at `apps/registry/static/r/index.json`.
- Treat these as generated copy-and-own artifacts unless a real hosted registry URL and clean-consumer workflow are verified.
- Do not invent `@coss-svelte/*` shadcn aliases or a hosted `/r/` domain.
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
