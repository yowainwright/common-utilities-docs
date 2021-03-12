# Installation

## Installing your desired utility

Common Utilities is a monorepo. To install the dependency you like, add the name of the utility after typing `@common-utilities`

```bash
$ pnpm install @common-utilities/<utililty-name>

# example 
$ pnpm install @common-utilities/merge-objects
```

{% hint style="info" %}
You don't need to use Pnpm as a package manager. Npm and Yarn are also supported.
{% endhint %}

### Quick Usage

Once you've installed your package. Use it as necessary:

{% code title="some-file-using-deep-merge.js" %}
```javascript
import { mergObjects } from '@common-utilities/merge-objects';

mergeObjects({ foo: 'bar' }, { baz: 'biz' }) // 🎉
```
{% endcode %}



