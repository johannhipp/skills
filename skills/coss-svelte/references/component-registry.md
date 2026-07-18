# coss-svelte component registry

Use this index to select a primitive, then read its guide before writing code. The current source has **54 components**: **50 stable**, **3 experimental**, and **1 deferred**.

Status is part of the API contract: do not import deferred components, and name experimental limitations in user-facing guidance.

## Overlays & Popups

- [Alert Dialog](./primitives/alert-dialog.md) — A modal dialog that interrupts the user workflow for critical confirmations. (stable; bits)
- [Command](./primitives/command.md) — A command palette component built with Dialog and Autocomplete for searching and executing commands. (stable; compound)
- [Dialog](./primitives/dialog.md) — A modal overlay for displaying content that requires user interaction. (stable; bits)
- [Menu](./primitives/menu.md) — A list of actions or options revealed on demand. (stable; compound)
- [Popover](./primitives/popover.md) — A floating container that appears near a trigger element. (stable; bits)
- [Preview Card](./primitives/preview-card.md) — A rich preview component for displaying linked content. (stable; bits)
- [Sheet](./primitives/sheet.md) — A flyout that opens from the side of the screen, based on the dialog component. (stable; compound)
- [Tooltip](./primitives/tooltip.md) — A small overlay that provides contextual information on hover or focus. (stable; bits)
- [Drawer](./primitives/drawer.md) — An experimental Dialog-backed drawer surface without swipe, snap-point, or nested-drawer parity. (experimental; custom)

## Selection & Input

- [Autocomplete](./primitives/autocomplete.md) — An input that suggests options as you type. (stable; compound)
- [Calendar](./primitives/calendar.md) — A date picker for selecting single dates, ranges, or multiple dates. (stable; bits)
- [Combobox](./primitives/combobox.md) — An input combined with a list of predefined items to select. (stable; bits)
- [Date Picker](./primitives/date-picker.md) — A date selection component, often combined with a calendar in a popover or input. (stable; compound)
- [Input](./primitives/input.md) — A native input element. (stable; native)
- [Input Group](./primitives/input-group.md) — A flexible component for grouping inputs with addons, buttons, and other elements. (stable; compound)
- [OTP Field](./primitives/otp-field.md) — A segmented input for one-time passwords and verification codes. (stable; bits)
- [Select](./primitives/select.md) — A common form component for choosing a predefined value in a dropdown menu. (stable; bits)
- [Slider](./primitives/slider.md) — A draggable control for selecting values from a continuous range. (stable; bits)
- [Textarea](./primitives/textarea.md) — A multi-line text input for longer content. (stable; native)
- [Number Field](./primitives/number-field.md) — A specialized input for numeric values with increment/decrement controls. (deferred; custom)

## Forms & Validation

- [Field](./primitives/field.md) — A wrapper component for form inputs with labels and validation. (stable; compound)
- [Fieldset](./primitives/fieldset.md) — A group of related form fields with a common label. (stable; native)
- [Form](./primitives/form.md) — A styled native form wrapper; validation and submission behavior remain application-owned. (stable; native)
- [Label](./primitives/label.md) — Renders an accessible label associated with controls. (stable; bits)

## Toggle & Choice

- [Checkbox](./primitives/checkbox.md) — A binary toggle input for selecting one or multiple options. (stable; bits)
- [Checkbox Group](./primitives/checkbox-group.md) — A layout and semantics wrapper for related checkboxes; each Checkbox owns its state. (stable; custom)
- [Radio Group](./primitives/radio-group.md) — A set of mutually exclusive options presented as radio buttons. (stable; bits)
- [Switch](./primitives/switch.md) — A toggle control for binary on/off states. (stable; bits)
- [Toggle](./primitives/toggle.md) — A button that switches between two states. (stable; bits)
- [Toggle Group](./primitives/toggle-group.md) — A group of toggle buttons where one or multiple can be selected. (stable; bits)

## Layout & Navigation

- [Accordion](./primitives/accordion.md) — A set of collapsible panels with headings. (stable; bits)
- [Breadcrumb](./primitives/breadcrumb.md) — Displays the path to the current resource using a hierarchy of links. (stable; native)
- [Collapsible](./primitives/collapsible.md) — A component that toggles visibility of content sections. (stable; bits)
- [Pagination](./primitives/pagination.md) — A pagination with page navigation, next and previous links. (stable; bits)
- [Scroll Area](./primitives/scroll-area.md) — A container with custom scrollbars for overflow content. (stable; bits)
- [Tabs](./primitives/tabs.md) — A component for toggling between related panels on the same page. (stable; bits)
- [Toolbar](./primitives/toolbar.md) — A container for grouping related actions or controls. (stable; bits)
- [Sidebar](./primitives/sidebar.md) — An experimental collapsible navigation shell with provider-backed open state. (experimental; compound)

## Content & Display

- [Avatar](./primitives/avatar.md) — A visual representation of a user or entity. (stable; bits)
- [Badge](./primitives/badge.md) — A small status indicator or label component. (stable; native)
- [Card](./primitives/card.md) — A content container for grouping related information. (stable; native)
- [Empty](./primitives/empty.md) — A container for displaying empty state information. (stable; native)
- [Frame](./primitives/frame.md) — A container component for displaying content in a frame. (stable; native)
- [Group](./primitives/group.md) — A container component for grouping related content with consistent styling. (stable; native)
- [Kbd](./primitives/kbd.md) — A component for displaying keyboard keys and shortcuts. (stable; native)
- [Separator](./primitives/separator.md) — A visual divider for separating content sections. (stable; bits)
- [Table](./primitives/table.md) — A structured data display component with rows and columns. (stable; native)

## Feedback & Status

- [Alert](./primitives/alert.md) — A callout for displaying important information. (stable; native)
- [Meter](./primitives/meter.md) — A visual representation of a value within a known range. (stable; bits)
- [Progress](./primitives/progress.md) — A visual indicator showing the completion status of a task. (stable; bits)
- [Skeleton](./primitives/skeleton.md) — A placeholder for loading content. (stable; native)
- [Spinner](./primitives/spinner.md) — An indicator that can be used to show a loading state. (stable; native)
- [Toast](./primitives/toast.md) — An experimental local notification surface with bindable visibility, not a queue or manager API. (experimental; custom)

## Actions

- [Button](./primitives/button.md) — A button or a component that looks like a button. (stable; native)
