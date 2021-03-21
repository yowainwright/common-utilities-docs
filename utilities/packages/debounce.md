# Debounce 🏓

## @common-utilities/debounce 🧰 

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![npm version](https://camo.githubusercontent.com/df001f73015e15cf9b0b95aa883b46c7b96b02699e9b5c28a9fc11e83131a5ed/68747470733a2f2f62616467652e667572792e696f2f6a732f253430636f6d6d6f6e2d7574696c69746965732532466465626f756e63652e737667)](https://badge.fury.io/js/%40common-utilities%2Fdebounce)

**Debounce** is a common function that waits a set amount of time before invoking a callback.

### Install

```text
yarn add @common-utilities/debounce -D
```

### Usage

```text
let result = 1
const add1 = (val) => {
  result = val + 1
}
debounce(add1, 1000)(1) // returns 2, after 1 second
```

### Common Utilities 🧰

**No cruft. No bloat. No dependencies.**

Simple, typed, functional, documented, and tested javascript utility functions.

View other [**common utilities**](https://github.com/yowainwright/common-utilities) on Github.

