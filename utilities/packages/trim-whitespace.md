# Trim-whitespace ⬜️

## @common-utilities/trim-whitespace 🧰

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![npm version](https://camo.githubusercontent.com/1566aaba6aabdc38121377e39408d3f8ca06bf18ebe0422313a7392df5849857/68747470733a2f2f62616467652e667572792e696f2f6a732f253430636f6d6d6f6e2d7574696c69746965732532467472696d2d776869746573706163652e737667)](https://badge.fury.io/js/%40common-utilities%2Ftrim-whitespace)

A common function for trimming whitespace without regex!

### Install

```text
yarn add @common-utilities/trim-whitespace -D
```

### Function

```text
const trimWhitespace = (string) =>
  string
    .trim()
    .split('  ')
    .map((word) => word.trim())
    .filter((word) => word !== '')
    .join(' ')
```

### Usage

```text
trimWhitespace('    This is some  really crazy.     string.   ')
// This is some really crazy. string.
```

### Common Utilities 🧰

**No cruft. No bloat. No dependencies.**

Simple, typed, functional, documented, and tested javascript utility functions.

View other [**common utilities**](https://github.com/yowainwright/common-utilities) on Github.

