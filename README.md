# Astro Color Scheme

Astro Color Scheme is a fully headless dark mode theme toggle for Astro.

[**Live Demo on Stackblitz →**](#)

[**Live Demo on Stablo Template →**](https://stablo-astro.web3templates.com/)

## Installation

```
npm install astro-color-scheme
# or
pnpm add astro-color-scheme
```

## Basic Usage

You can toggle the theme using `button`, `select` or `checkbox` inside the `<ThemeSwitch>`.

```jsx
---
import { ThemeSwitch } from "astro-color-scheme";
---

<div>
  <ThemeSwitch>
    <button>Toggle Theme</button>
  </ThemeSwitch>
</div>
```

<details>
<summary>Advanced Example</summary>

**Using Select:**

```jsx
---
import { ThemeSwitch } from "astro-color-scheme";
---

<div>
  <ThemeSwitch strategy="select" defaultTheme="system">
    <select>
      <option value="system">System</option>
      <option value="dark">Dark</option>
      <option value="light">Light</option>
    </select>
  </ThemeSwitch>
</div>
```

</details>

<details>
<summary>Set theme without any toggle</summary>

```jsx
---
import { ThemeSwitch } from "astro-color-scheme";
---

<div>
  <ThemeSwitch defaultTheme="dark"/>
</div>
```

</details>

## Options

Options for `ThemeSwitch`

| option         | required                     | notes                                                           |
| -------------- | ---------------------------- | --------------------------------------------------------------- |
| `strategy`     | `required` if you use toggle | Possible values: `button`, `checkbox` or `select`               |
| `defaultTheme` | `optional`                   | Default: `system`, Possible values: `light`, `dark` or `system` |

Elements Allowed for Toggle inside `ThemeSwitch` are `<button>`, `checkbox` & `<select>`

```html
<!-- Button -->
<button>Toggle Theme</button>

<!-- Checkbox -->
<input type="checkbox" />

<!-- Select -->
<select>
  <option value="system">System</option>
  <option value="dark">Dark</option>
  <option value="light">Light</option>
</select>
```

## Customizations

As a headless plugin, You are free to add your own styles and icons based on the theme. Here's an example shows usage of Astro Icon.

```jsx
---
import { Icon } from "astro-icon";
import { ThemeSwitch } from "astro-color-scheme";
---

<div>
  <ThemeSwitch>
    <button>
      <span class="sr-only">Toggle Theme</span>
      <Icon class="dark:hidden" name="heroicons-outline:sun" />
      <Icon class="hidden dark:block" name="heroicons-outline:moon" />
    </button>
  </ThemeSwitch>
</div>
```

This plugin also supports custom checkbox switch with animations. Just use `strategy="checkbox"` and add your content. By default we add `dark/light` class into the `html` as well as `data-theme` attribute. Here's how it would look like:

```html
<html lang="en" class="dark" data-theme="dark"></html>
```

## Tailwind CSS

This plugin should work well with regular CSS as well as Tailwind CSS. You can style the `dark` mode using `dark:` modifier to add custom icon based on the chosen theme.

</details>

## Contribute

Please create an issue.

## Credits

Copyright ©️ 2023-2099. [Surjith S M](https://twitter.com/surjithctly).