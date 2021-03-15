# Compose

## @common-utilities/compose 🧰 🚂

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![npm version](https://camo.githubusercontent.com/1ed535ffe63517f039bb4a9d748804a62e95be144004da8e5257871588abb31a/68747470733a2f2f62616467652e667572792e696f2f6a732f253430636f6d6d6f6e2d7574696c6974696573253246636f6d706f73652e737667)](https://badge.fury.io/js/%40common-utilities%2Fcompose)

**Compose** is a common function composed of function arguments which returns their value to the next function until returning a final value.

### Install

```text
yarn add @common-utilities/compose -D
```

### Function

```text
const compose = (...fns) => (val) => fns.reduceRight((fnVal, fn) => fn(fnVal), val)
```

### Usage

```text
const add1 = (val) => val + 1
const subtract2 = (val) => val - 2
const multiplyBy3 = (val) => val * 3
const result = compose(add1, subtract2, multiplyBy3)
// result(3) // 5 (3 + 1 - 3 * 5)
```

### Common Utilities 🧰

**No cruft. No bloat. No dependencies.**

Simple, typed, functional, documented, and tested javascript utility functions.

View other [common utilities](https://github.com/yowainwright/common-utilities) on Github.

