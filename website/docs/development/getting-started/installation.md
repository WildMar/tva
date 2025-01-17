---
sidebar_position: 1
tags: [Development, Installation, Fonts, Icons, Assets, Mobile]
---

# Installation

:::caution

This page is a work in progress.

:::

Install TVA, Pluralsight's headless UI framework.

TVA is available as a set of [npm packages](https://github.com/pluralsight/tva) for web and our `tokens` package is compatable for iOS, Swift, Android, and Kotlin.

## npm

For the entire kitchen sink up front, just install the `components` and `icons` packages.

```bash npm2yarn
npm install @pluralsight/tva-components @pluralsight/tva-icons
```

Or if you want maximum flexibility, just install the `tokens` package:

```bash npm2yarn
npm install @pluralsight/tva-tokens
```

## PS TT Commons font

TVA was designed with [PS TT Commons](https://github.com/pluralsight/tva) in mind. So be sure to follow the [typography instructions](https://github.com/pluralsight/tva). For the best results, install via an HTML `link` tag:

```
<link
  rel="stylesheet"
  href="https://...TBD"
/>
```

Each "component" uses a [variable font](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts/Variable_Fonts_Guide) declaration to provide all weights programmatically. IE 11 does not support variable fonts, so any IE users will get the sans-serif fallback.

## Font icons

To use the font `Icon` component, you must first add the TVA [icons font](https://github.com/pluralsight/tva). For the best results, install via a HTML `link` tag:

```
<link
  rel="stylesheet"
  href="https://...TBD"
/>
```

## SVG icons

In order to use prebuilt SVG TVA icons, such as those found in the [icons demos](https://github.com/pluralsight/tva) you must first install the [@pluralsight/tva-icons](https://github.com/pluralsight/tva) package:

```bash npm2yarn
npm install @pluralsight/tva-icons
```

## Mobile Assets

Our `tokens` package will also deliver all of our icons and fonts via assets for each mobile platform we support. :heart:

## Design resources

<!-- TODO: Add Figma "download" icon/link -->

A set of reusable components for design tools is available, designed to match the web components and to help you craft great products:

- [Figma](https://github.com/pluralsight/tva): A large UI kit with over 62 handcrafted TVA components.
