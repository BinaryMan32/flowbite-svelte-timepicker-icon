# Flowbite Svelte Timepicker Icon

Project to demonstrate issues with the [Flowbite Svelte Timepicker][timepicker] `icon` field.

[timepicker]: https://flowbite-svelte.com/docs/forms/timepicker

## Project Creation

```bash
pnpx sv create
```

(Accepted all defaults)

Following instructions at [Quickstart - Flowbite Svelte][quickstart]

```bash
npx sv add tailwindcss
```

(Enabled `forms` plugin)

Add `flowbite-svelte`:

```bash
pnpm i -D flowbite-svelte flowbite flowbite-svelte-icons
```

Updated `src/app.css` as documented in [Quickstart - Configuration][quickstart-configuration].

Modified `src/routes/+page.svelte` to match [Flowbite Svelte Default timepicker][default-timepicker] example.

[quickstart]: https://flowbite-svelte.com/docs/pages/quickstart
[quickstart-configuration]: https://flowbite-svelte.com/docs/pages/quickstart#Configuration
[default-timepicker]: https://flowbite-svelte.com/docs/forms/timepicker#Default_timepicker

## Verified

Verified the issue is fixed in `flowbite-svelte` `1.0.2`.

## Issues

This is now fixed, see the `Verified` section above.
To see the original issue, check the `broken` branch.

Running `svelte-check` as shown below should pass:

```bash
pnpm check
```

However, it returns the error:

```text
.../flowbite-svelte-timepicker-icon/src/routes/+page.svelte:6:2
Error: Property 'icon' is missing in type '{}' but required in type '{ id?: string | undefined; endId?: string | undefined; value?: string | undefined; endValue?: string | undefined; min?: string | undefined; max?: string | undefined; required?: boolean | undefined; ... 15 more ...; columns?: 1 | ... 3 more ... | undefined; }'. (js)
<Label>Select Time:</Label>
<Timepicker />
```

Switching to the [Timepicker with icon][timepicker-icon] example returns a different error:

```text
.../flowbite-svelte-timepicker-icon/src/routes/+page.svelte:7:13
Error: Type 'Component<Props, {}, "">' is not assignable to type 'ComponentType'.
  Type 'Component<Props, {}, "">' is not assignable to type 'new (options: ComponentConstructorOptions<Record<string, any>>) => SvelteComponent<Record<string, any>, any, any>'.
    Type 'Component<Props, {}, "">' provides no match for the signature 'new (options: ComponentConstructorOptions<Record<string, any>>): SvelteComponent<Record<string, any>, any, any>'. (js)
<Label>Select Time (Flowbite Icon):</Label>
<Timepicker icon={ClockSolid} />
```

[timepicker-icon]: https://flowbite-svelte.com/docs/forms/timepicker#Timepicker_with_icon
