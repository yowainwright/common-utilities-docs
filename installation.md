# Installation

## Installing your desired utility

Common Utilities is a monorepo. To install the dependency you like, add the name of the utility after typing `@common-utilities`

```bash
$ pnpm install @common-utilities/<utililty-name>

# example 
$ pnpm install @common-utilities/deep-merge
```

{% hint style="info" %}
You don't need to use Pnpm as a package manager. Npm and Yarn are also supported.
{% endhint %}

Once you're strong enough, save the world:

{% code title="some-file-using-deep-merge.js" %}
```javascript
import { deepMerge } from '@common-utilities/deep-merge';
```
{% endcode %}



