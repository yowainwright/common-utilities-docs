# Trace

## @common-utilities/trace 🧰👤

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![npm version](https://camo.githubusercontent.com/76d6f0d9dcf0ef9cab8d149f661a87fc73c83eb11a0f70096cb557e2892c8b87/68747470733a2f2f62616467652e667572792e696f2f6a732f253430636f6d6d6f6e2d7574696c697469657325324674726163652e737667)](https://badge.fury.io/js/%40common-utilities%2Ftrace)

A common function for tracing values.

### Install

```text
yarn add @common-utilities/trace -D
```

### Function

```text
const trace = (label) => (value) => {
  console.log(`${label}: ${value}`)
  return value
}
```

### Usage

```text
trace('number')(2)
// logs number 2, awe s**t
```

### Common Utilities 🧰

**No cruft. No bloat. No dependencies.**

Simple, typed, functional, documented, and tested javascript utility functions.

View other [**common utilities**](https://github.com/yowainwright/common-utilities) on Github.

