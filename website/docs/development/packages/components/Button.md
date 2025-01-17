---
sidebar_position: 2
tags: [Development, Packages, Components, Button]
---

# Button

:::caution

This is **unreleased** documentation for TVA **components** package.

:::

The Button is used to call attention, perform an action, or to nagivate.

Buttons communicate actions that users can take. In your UI, they are typically found in places like:

- Modal windows
- Forms
- Skills Cards

## Basic Button

```typescript
interface Options {
  kind: 'default' || 'contained' || 'outlined'
  size: 'xs' || 's' || 'm' || 'l'
}

getButtonProps(options, js?: 'js'): ButtonProps
```

The `Button` comes with three variants: text (default), contained, and outlined.

```jsx
const tvaButtonProps = getButtonProps() // default
const tvaContainedButtonProps = getButtonProps({ kind: 'contained' })
const tvaOutlinedButtonProps = getButtonProps({ kind: 'outlined' })
```

## getButtonProps

The `Button` prop-getter returns an Object that contains all the a11y attributes needed along with all the styles for you to use in any fashion you like - or easily extend/overwrite when needed.

```js
{
  className: `tva-btn ${ourInternalStylesModule}`
  type: 'button'
}
```

:::note
If you are using **Styled-Components**, see "CSS in JS" section.
:::

### CSS in JS

If you prefer to use CSS-in-JS, simply pass a second argument of `'js'` to the `getButtonProps` function. This will return a stringified version of the styles along with a `styles` property for your choosing.

```js
{
  cssProps: `
    color: var(--TBD)
    background-color: var(--TBD)
    ...
  `,
  styles: {
    color: `${button.default.text.color.value}`,
    backgroundColor: `${button.default.background.value}`
    ...
  },
  type: 'button',
}
```

### Extending

There are times you may need to make a slight adjustment to the `Button` which is easy since we are giving you an Object. You can easily extend the Button in any way that you like.

Here is an example of using `styled-components` to extend a `Button` for a Form.

```jsx title=page/Login/components/SubmitButton.jsx
import styled from 'styled-components'
import { getButtonProps } from '@pluralsight/tva-components'

const tvaBtnProps = getButtonProps('contained', 'js')

const Button = styled.button`
  ...tvaBtnProps.cssProps,
  color: '#bfbfbf' // some custom color
`

function SubmitButton(props) {
  return <Button type="submit">{props.children}</Button>
}
```

## Buttons with icons and label

Our eyes/brain recognize logos more easily than plain text, so you might want to add icons to certain buttons to enhance the UX. For example, if you have a edit button you can label it with a `PencilIcon`.

```jsx title=components/EditButton.jsx
import { PencilIcon } from 'components/PencilIcon'
import { getButtonProps, getIconLabelProps } from '@pluralsight/tva-components'

const tvaButtonProps = getButtonProps({ kind: 'contained' })
const tvaIconLabelProps = getIconLabelProps()

function EditButton(props) {
  return (
    <button {...props} {...tvaButtonProps}>
      <PencilIcon {...tvaIconLabelProps} />
      <p>Edit</p>
    </button>
  )
}
```

## Icon Button

Icon buttons are commonly found in app bars, toolbars, or as an action such as "toggle".

```jsx title=components/EditIconButton.jsx
import { PencilIcon } from 'components/PencilIcon'
import { getIconButtonProps } from '@pluralsight/tva-components'

const tvaEditIconBtnProps = getButtonProps('edit profile')

function EditIconButton(props) {
  return (
    <button {...props} {...tvatvaEditIconBtnProps}>
      <PencilIcon />
    </button>
  )
}
```

## API

| Name                | Argument Type                             | Default                                  | Description                            |
| ------------------- | ----------------------------------------- | ---------------------------------------- | -------------------------------------- |
| `getButtonProps`    | **options**: ButtonOptions, **js?**: 'js' | **kind**: 'default', <br />**size**: 'm' | Get main button styles.                |
| `getIconLabelProps` |                                           |                                          | Get button with icon and label styles. |
| `getButtonProps`    | **ariaLabel**: string                     | 'icon button'                            | Get icon button styles.                |
