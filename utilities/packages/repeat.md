# Repeat 🔁

## @common-utilities/repeat 🧰

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![npm version](https://camo.githubusercontent.com/21cd018cd3484b76cd8de20075127aa80c0a9b33b92db8eef1de013c1e162670/68747470733a2f2f62616467652e667572792e696f2f6a732f253430636f6d6d6f6e2d7574696c69746965732532467265706561742e737667)](https://badge.fury.io/js/%40common-utilities%2Frepeat)

**Repeat** is a common function composed of function arguments that recursively invoke a callback function based on iterations returning a final value.

The repeat function can be used to replace while loops.

### Install

```text
yarn add @common-utilities/repeat -D
```

### Usage

```text
const add1 = (val) => val + 1
repeat(100)(add1)(0) // 100
```

### Common Utilities 🧰

**No cruft. No bloat. No dependencies.**

Simple, typed, functional, documented, and tested javascript utility functions.

View other [**common utilities**](https://github.com/yowainwright/common-utilities) on Github.

