# Introduction

[![Typed with TypeScript](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535)](https://camo.githubusercontent.com/69ea44e002591f4d18f9d1ee7660e8c49bbf4e673405eb058e3af515a193d376/68747470733a2f2f666c61742e62616467656e2e6e65742f62616467652f69636f6e2f54797065643f69636f6e3d74797065736372697074266c6162656c266c6162656c436f6c6f723d626c756526636f6c6f723d353535353535) [![lerna](https://camo.githubusercontent.com/3bc63f921dd60bac6d91aa900ef570c928b2aa4c2124ed23647e8fe9d2232853/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6d61696e7461696e6564253230776974682d6c65726e612d6363303066662e737667)](https://lerna.js.org/)

**No cruft. No bloat. No dependencies.**

Common Utilities is an ecosystem of simple utility JavaScript functions for everyday development. 

### Why?

Often engineers write simple functions to do simple things. There is always an option to reach for a heavier tool to do something like a **deep merge**. However, engineers can do something **simple** to satisfy their use-case.   
  
Common Utilities aims to provide functions for the **simple** use-case described above but with **types** and **tests**. This means engineers can use a smaller function from Common Utilities that looks much like something they would write quickly but not need to write tests or types because Common Utilities provides those things. Inversely, using a utility function from Common Utilities adds very little extra bloat for each utility used. 

### Comparison

If you're still undecided on Common Utilities here a few lines of comparison text to take you over the edge.

#### Common Utilities 🧰   or 1-line-of-code

Common Utilities provides an option to [1LOC](https://1loc.dev/) because each function can be imported rather than copied. This ensures that you don't need to write your own tests while knowing you're using easy-to-read tested code!

#### Common Utilities 🧰   or Utilities Libraries

Common Utilities provides an option focused on simplicity compared to [Ramba](https://ramdajs.com/) or [Lodash](https://lodash.com/) because it provides solutions to many common JavaScript utility functions in a basic way.

Where Ramba and Lodash provide better overall coverage for what each JavaScript utility does, they also are more challenging to quickly know if the code does what **you** need it to do.

Also, Libraries like [Ramda](https://ramdajs.com/#usage) and [Lodash](https://lodash.com/per-method-packages) may assume that you [tree shake](https://developer.mozilla.org/en-US/docs/Glossary/Tree_shaking) unused code in your build pipeline and are generally more bytes of code.



