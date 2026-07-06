# Migration Rules

## From COSS React or Base UI

- Port the visual and interaction contract, not the React implementation.
- Replace JSX with Svelte markup and event/binding syntax.
- Replace `className` with `class` only when passing classes is supported by the local component.
- Do not import `@base-ui/react`; use coss-svelte components backed by Bits UI or native markup.
- Do not use React hooks in Svelte examples.

## From shadcn or Radix

- Do not assume `asChild`, Radix data attributes, or shadcn file structure exists.
- Verify every component part against `coss-svelte` exports before using it.
- Prefer Svelte-native composition and documented coss-svelte anatomy.
- Keep accessibility behavior equivalent even when API names differ.

## From COSS particles

- Treat upstream particle descriptions as pattern inspiration until coss-svelte has registry-backed Svelte particle manifests.
- Do not paste React particle source into Svelte files.
