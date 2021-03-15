# Glossary

Below are sectioned descriptions and code usages of each implemented Common Utility. Read more about each common utility within each package's README!

[Compose](https://github.com/yowainwright/common-utilities#compose-) \| [Head](https://github.com/yowainwright/common-utilities#head-) \| [Pipe](https://github.com/yowainwright/common-utilities#pipe-) \| [Trace](https://github.com/yowainwright/common-utilities#trace-) \| [Repeat](https://github.com/yowainwright/common-utilities#repeat-) \| [Filter-Array](https://github.com/yowainwright/common-utilities#filter-array-) \| [Is-Object](https://github.com/yowainwright/common-utilities#is-object-) \| [Merge-Objects](https://github.com/yowainwright/common-utilities#merge-objects-) \| [String-interpolation](https://github.com/yowainwright/common-utilities#string-interpolation-) \| [Kebab-to-camel-string](https://github.com/yowainwright/common-utilities#kebab-to-camel-string-) \| [Trim-whitespace](https://github.com/yowainwright/common-utilities#trim-whitespace-) \| [Wait-until-defined](https://github.com/yowainwright/common-utilities#wait-until-defined-) \|

### Compose 🚂

[**Compose**](https://github.com/yowainwright/common-utilities/blob/master/packages/compose) is a common function that take the output from one function and automatically patches it to the input of the next function until it spits out the final value.

Compose is useful for computing a series of functions in a composed fashion improving code readability and testability.

**Function**

```text
const compose = (...fns) => (patchedValue) => fns.reduceRight((fnVal, fn) => fn(fnVal), patchedValue)
```

**Usage**

```text
const result = compose(add1, subtract3, multipleBy5)
// result(3) // 5 (3 + 1 - 3 * 5)
```

### Head 👤

[**Head**](https://github.com/yowainwright/common-utilities/blob/master/packages/head) is a common function for return the value of the first item in an Array.

**Function**

```text
const head = ([first]) => first
```

**Usage**

```text
head([0, 1, 2, 3, 4]) // 01
```

#### Pipe ⛓

[**Pipe**](https://github.com/yowainwright/common-utilities/blob/master/packages/pipe) is a common function that take the output from one function and automatically patches it to the input of the next function until it spits out the final value in the opposite order of Compose.

Like compose, Pipe is useful for computing a series of functions in a composed fashion improving code readability and testability but in the opposite order of Compose.

**Function**

```text
const pipe = (...fns) => (patchedValue) => fns.reduce((fnVal, fn) => fn(fnVal), patchedValue)
```

**Usage**

```text
const result = pipe(add1, subtract2, multipleBy3)
// result(3) // 8 (3 * 3 - 2 + 1)
```

### Repeat 🖋

[**Repeat**](https://github.com/yowainwright/common-utilities/blob/master/packages/repeat) is a common function composed of function arguments which recursively invoke a callback function based on iterations returning a final value.

Repeat is useful for declaritively performing a while loop, making it more testable.

**Function**

```text
const repeat = (iterations) => (callback) => (initialValue) =>
  iterations === 0 ? initialValue : repeat(iterations - 1)(callback)(callback(initialValue))
```

**Usage**

```text
const add1 = (val) => val + 1
repeat(100)(add1)(0) // 100
```

### Filter-Array 🧹

[**Filter Array**](https://github.com/yowainwright/common-utilities/blob/master/packages/filter-array) is a common function a common function that removes deplicate items from an array.

Filter is useful for ensuring an array is exact.

**Function**

```text
const filterArray = (arr) => arr.filter((item, index, self) => self.indexOf(item) === index)
```

**Usage**

```text
filterArray(['test', 'test', 'foo', 'bar', 'biz']) // ['test', 'foo', 'bar', 'biz'])
```

### Is-Object 🎛

[**IsObject**](https://github.com/yowainwright/common-utilities/blob/master/packages/is-object) is a common function for knowings whether data is of Object type. This function comes with `isArray` and `isOfObjectTypes` helper methods.

Is object is useful for determining that an object is an object **and** not an array.

**Function**

```text
const isArray = (item) => Array.isArray(item)
const isOfObjectType = (item) => item !== null && typeof item === 'object'
const isObject = (item) => isOfObjectType(item) && !isArray(item)
```

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

**Function**

```text
const mergeObjects = (item, otherItem) => {
  if ((!isObject(item) && !isArray(item)) || (!isObject(otherItem) && !isArray(otherItem))) {
    return item
  }
  if (isArray(item) && isArray(otherItem)) {
    return filterArray([...item, ...otherItem])
  }

  return filterArray([...Object.keys(item), ...Object.keys(otherItem)]).reduce((acc, key: string) => {
    if (typeof acc[key] === 'undefined') {
      acc[key] = otherItem[key]
    } else if (isObject(acc[key]) || isArray(acc[key])) {
      acc[key] = mergeObjects(item[key], otherItem[key])
    } else if (acc[key] !== otherItem[key] && typeof otherItem[key] !== 'undefined') {
      acc[key] = otherItem[key]
    }
    return acc
  }, item)
}
```

**Usage**

```text
mergeObjects({ foo: 'bar' }, { baz: 'biz' }) // { foo: 'bar', baz: 'biz' }
```

#### String-interpolation 🧵

[**String Interpolation**](https://github.com/yowainwright/common-utilities/blob/master/packages/string-interpolation) is a common function for interpolating variables in strings.

String Interpolation is useful for adding dynamic data to strings.

**Function**

```text
const stringInterpolation = (str, arr) =>
  !str || !arr
    ? arr.reduce((generatedStr, item) => {
        const dynamicKey = Object.keys(item).toString()
        return generatedStr.replace(`#{${dynamicKey}}`, item[dynamicKey])
      }, str)
    : str
```

**Usage**

```text
stringInterpolation('This string has #{dynamicData}', [{ dynamicData: 'a knot in it' }])
// => 'This string has a knot in i
```

### Kebab-to-camel-string 🍢🐫

[**Kebab to Camel String**](https://github.com/yowainwright/common-utilities/blob/master/packages/kebab-to-camel-string) is a common function for returning a kebab string as a camel string.

Kebab to Camel String is useful for switching objects from kebab case to camel case which is more usable in JavaScript.

**Function**

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

**Usage**

```text
// string
kebabToCamelString('test-thing')
// testThing

// object
kebabToCamelStringsInObject({ 'test-thing': 'foo' })
// { testThing: 'foo' }
```

### Trim-whitespace 🍢🐫

[**Trim Whitespace**](https://github.com/yowainwright/common-utilities/blob/master/packages/trim-whitespace) is a common function for returning a string with trimmed text.

Trim-whitespace is useful for removing extra spaces from inputed strings.

**Function**

```text
const trimWhitespace = (string) =>
  string
    .trim()
    .split('  ')
    .map((word) => word.trim())
    .filter((word) => word !== '')
    .join(' ')
```

**Usage**

```text
trimWhitespace('    This is some  really crazy.     string.   ')
// This is some really crazy. string.
```

### Wait-until-defined ⌚️

[**Wait-until-defined**](https://github.com/yowainwright/common-utilities/blob/master/packages/wait-until-defined) is a common function for waiting until data is defined via a callback which returns a boolean.

Wait-until-defined is useful for waiting until some data type is defined.

**Function**

```text
const wait = (timeout) => new Promise((resolve) => setTimeout(resolve, timeout))
const isDefined = (callbackFn) => new Promise((resolve) => resolve(callbackFn()))
const checkDefinition = async (callbackFn, timeout, count) => {
  const definition = await isDefined(callbackFn)
  if (definition) {
    return definition
  } else {
    await wait(timeout)
    return checkDefinition(callbackFn, timeout, count - 1)
  }
}
const waitUntilDefined = async (callbackFn, interval, timeout) => {
  const count = timeout / interval
  const definition = await checkDefinition(callbackFn, interval, count)
  return definition
}
```

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

