# Pipe ⛓

## @common-utilities/pipe 🧰

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![npm version](https://camo.githubusercontent.com/05cd3627ca0e7a4aae3977f755cbc5c907bc75a69e08d9396e9a987e57625065/68747470733a2f2f62616467652e667572792e696f2f6a732f253430636f6d6d6f6e2d7574696c6974696573253246706970652e737667)](https://badge.fury.io/js/%40common-utilities%2Fpipe)

**Pipe** is a common function composed of function arguments that returns their value to the next function until returning a final value in the opposite order of **compose**.

### Install

```text
yarn add @common-utilities/pipe -D
```

### Function

```text
const pipe = (...fns) => (patchedValue) => fns.reduce((fnVal, fn) => fn(fnVal), patchedValue)
```

### Usage

```text
const add1 = (val) => val + 1
const subtract2 = (val) => val - 2
const multiplyBy3 = (val) => val * 3
const result = pipe(add1, subtract2, multiplyBy3)
result(3) // 8 (3 * 3 - 2 + 1)
```

### Common Utilities 🧰

**No cruft. No bloat. No dependencies.**

Simple, typed, functional, documented, and tested javascript utility functions.

View other [**common utilities**](https://github.com/yowainwright/common-utilities) on Github.

