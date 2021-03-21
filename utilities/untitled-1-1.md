# Glossary 📒

Below are sectioned descriptions and code usages of each implemented Common Utility. Read more about each common utility within each package's README!

### Compose 🚂

[**Compose**](https://github.com/yowainwright/common-utilities/blob/master/packages/compose) is a common function that take the output from one function and automatically patches it to the input of the next function until it spits out the final value.

Compose is useful for computing a series of functions in a composed fashion improving code readability and testability.

**Usage**

```text
const result = compose(add1, subtract3, multipleBy5)
// result(3) // 5 (3 + 1 - 3 * 5)
```

### Head 👤

[**Head**](https://github.com/yowainwright/common-utilities/blob/master/packages/head) is a common function for return the value of the first item in an Array.

**Usage**

```text
head([0, 1, 2, 3, 4]) // 01
```

#### Pipe ⛓

[**Pipe**](https://github.com/yowainwright/common-utilities/blob/master/packages/pipe) is a common function that take the output from one function and automatically patches it to the input of the next function until it spits out the final value in the opposite order of Compose.

Like compose, Pipe is useful for computing a series of functions in a composed fashion improving code readability and testability but in the opposite order of Compose.

**Usage**

```text
const result = pipe(add1, subtract2, multipleBy3)
// result(3) // 8 (3 * 3 - 2 + 1)
```

### Repeat 🖋

[**Repeat**](https://github.com/yowainwright/common-utilities/blob/master/packages/repeat) is a common function composed of function arguments which recursively invoke a callback function based on iterations returning a final value.

Repeat is useful for declaritively performing a while loop, making it more testable.

**Usage**

```text
const add1 = (val) => val + 1
repeat(100)(add1)(0) // 100
```

### Filter-Array 🧹

[**Filter Array**](https://github.com/yowainwright/common-utilities/blob/master/packages/filter-array) is a common function a common function that removes deplicate items from an array.

Filter is useful for ensuring an array is exact.

**Usage**

```text
filterArray(['test', 'test', 'foo', 'bar', 'biz']) // ['test', 'foo', 'bar', 'biz'])
```

### Is-Object 🎛

[**IsObject**](https://github.com/yowainwright/common-utilities/blob/master/packages/is-object) is a common function for knowings whether data is of Object type. This function comes with `isArray` and `isOfObjectTypes` helper methods.

Is object is useful for determining that an object is an object **and** not an array.

**Usage**

isArray

```text
isArray(['test', 'test']) // true
isArray({ foo: 'test' }) // false
```

isOfObjectType

```text
isOfObjectType(['test', 'test']) // true
isOfObjectType({ foo: 'test' }) // true
isOfObjectType(9) // false
isOfObjectType('string') // false
isOfObjectType(null) // false
isOfObjectType(undefined) // false
```

isObject

```text
isObject(['test', 'test']) // false
isObject({ foo: 'test' }) // true
```

### Merge-Objects👯‍♂️

[**Merge Objects**](https://github.com/yowainwright/common-utilities/blob/master/packages/merge-objects) is a common function for merging two objects deeply.

Merge Objects is useful for merging objects with nested object and/or array properties.

**Usage**

```text
mergeObjects({ foo: 'bar' }, { baz: 'biz' }) // { foo: 'bar', baz: 'biz' }
```

#### String-interpolation 🧵

[**String Interpolation**](https://github.com/yowainwright/common-utilities/blob/master/packages/string-interpolation) is a common function for interpolating variables in strings.

String Interpolation is useful for adding dynamic data to strings.

**Usage**

```text
stringInterpolation('This string has #{dynamicData}', [{ dynamicData: 'a knot in it' }])
// => 'This string has a knot in i
```

### Kebab-to-camel-string 🍢🐫

[**Kebab to Camel String**](https://github.com/yowainwright/common-utilities/blob/master/packages/kebab-to-camel-string) is a common function for returning a kebab string as a camel string.

Kebab to Camel String is useful for switching objects from kebab case to camel case which is more usable in JavaScript.

**Usage**

```text
// string
kebabToCamelString('test-thing')
// testThing

// object
kebabToCamelStringsInObject({ 'test-thing': 'foo' })
// { testThing: 'foo' }
```

### Trim-whitespace ✂️

[**Trim Whitespace**](https://github.com/yowainwright/common-utilities/blob/master/packages/trim-whitespace) is a common function for returning a string with trimmed text.

Trim-whitespace is useful for removing extra spaces from inputed strings.

**Usage**

```text
trimWhitespace('    This is some  really crazy.     string.   ')
// This is some really crazy. string.
```

### Wait-until-defined ⌚️

[**Wait-until-defined**](https://github.com/yowainwright/common-utilities/blob/master/packages/wait-until-defined) is a common function for waiting until data is defined via a callback which returns a boolean.

Wait-until-defined is useful for waiting until some data type is defined.

**Usage**

```text
setTimeout(() => (window.Test = 'yay'), 2000)
const hasWindowTest = () => window.Test === 'test'
const test = async () => {
  const check = await waitUntilDefined(hasWindowTest, 50, 3000)
  return check
}
// true
```

### Debounce 🏓

[**Debounce**](https://github.com/yowainwright/common-utilities/blob/master/packages/bedounce) is a common function that waits a set amount of time before invoking a callback.

Debounce is useful for ensuring that a function invocation doesn't happen too frequently.

**Usage**

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

