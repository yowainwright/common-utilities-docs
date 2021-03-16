# Kebab-to-camel-string 🍢🐫

## @common-utilities/kebab-to-camel-string 🧰

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![npm version](https://camo.githubusercontent.com/04cfcc68c6269039e67fcdf0c597990df58c6dc70f2a17b3debf23de27470258/68747470733a2f2f62616467652e667572792e696f2f6a732f253430636f6d6d6f6e2d7574696c69746965732532466b656261622d746f2d63616d656c2d737472696e672e737667)](https://badge.fury.io/js/%40common-utilities%2Fkebab-to-camel-string)

**kebabToCamelString** is a common function for returning a kebab string as a camel string.

### Install

```text
yarn add @common-utilitiee/kebab-to-camel-string -D
```

### Function

```text
// string
const kebabToCamelString = (kebabString) =>
  kebabString
    .split('-')
    .map((camelString, i) =>
      i === 0 ? camelString : camelString ? `${camelString.charAt(0).toUpperCase()}${camelString.slice(1)}` : '',
    )
    .join('')

// object
const kebabToCamelStringsInObject = (kebabObjectStrings) =>
  Object.keys(kebabObjectStrings).length
    ? Object.entries(kebabObjectStrings)
        .map(([kebabKey, value]) => [`${kebabToCamelString(kebabKey)}`, value])
        .reduce((flags, [key, value]) => Object.assign(flags, { [key]: value }), {})
    : {}
```

### Usage

```text
// string
kebabToCamelString('test-thing')
// testThing

// object
kebabToCamelStringsInObject({ 'test-thing': 'foo' })
// { testThing: 'foo' }
```

### Common Utilities 🧰

**No cruft. No bloat. No dependencies.**

Simple, typed, functional, documented, and tested javascript utility functions.

View other [**common utilities**](https://github.com/yowainwright/common-utilities) on Github.

