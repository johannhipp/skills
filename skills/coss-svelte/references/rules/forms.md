# Form rules

## Use Field context

Use `Field` around Input, Textarea, InputGroupInput, or InputGroupTextarea so IDs and accessible state can be coordinated.

```svelte
<Field label="Email" description="Used for account updates" error={invalid ? "Enter a valid email." : ""} {invalid} required>
	<Input bind:value={email} name="email" type="email" />
</Field>
```

- Use either Field convenience props (`label`, `description`, `error`) or FieldLabel/FieldDescription/FieldError children, not both.
- Set `invalid`, `required`, and `disabled` on Field; descendant field-aware controls inherit IDs, `aria-describedby`, `aria-invalid`, and native state.
- Keep errors conditional and set `invalid` consistently with their visibility.
- Use Fieldset/FieldsetLegend for related controls and CheckboxGroup/RadioGroup for choice collections.

## Treat Form as native

`Form` is a styled native `<form>` wrapper. It does not parse values, run Zod, manage touched state, or provide React-style form context.

- Handle `onsubmit` directly or integrate SvelteKit `enhance`, Superforms, formsnap, Zod, or Valibot at the application layer.
- Set `name` on submitted controls.
- Set explicit input and button types.
- Keep submit buttons inside the form. In Dialog/Sheet/Drawer layouts, use `Form class="contents"` around both panel and footer.

## Respect current binding declarations

- Input and InputGroupInput expose `bind:value`.
- Checkbox and Switch expose `bind:checked`; Checkbox also exposes `bind:indeterminate`.
- Select, Combobox, Autocomplete, RadioGroup, OTPField, Slider, and related roots expose the bindings documented in their primitive guides.
- Textarea and InputGroupTextarea currently forward native attributes but do not declare a bindable `value`. Verify the installed declaration before writing `bind:value`; use an explicit `value`/`oninput` flow when necessary.

## Keep InputGroup order

Place InputGroupInput or InputGroupTextarea before InputGroupAddon in DOM order. Use the addon's `align` prop for visual placement.
