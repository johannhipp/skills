# Form Rules

- Use `Form`, `Field`, `FieldLabel`, `FieldDescription`, `FieldError`, and input components together for accessible form rows.
- Keep labels associated with controls and errors close to the field they describe.
- Do not hard-code a validation library into core examples unless the target project already uses it.
- SvelteKit `enhance`, Superforms, formsnap, Zod, and Valibot are adapter-level choices, not required by coss-svelte core.
- Use explicit `type` on buttons inside forms.
- Keep invalid, disabled, required, helper, and error states visible through documented component props/parts when available.
