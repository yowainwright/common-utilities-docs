# Usage

### Post Install

After installing your package, usage should be self-explanatory.

{% code title="some-javascript-file.js" %}
```javascript
import { mergObjects } from '@common-utilities/merge-objects';

mergeObjects({ foo: 'bar' }, { baz: 'biz' }) // 🎉
```
{% endcode %}

But there's more. All Common Utilities are built using Typescript so they come with types

{% code title="some-typescript-file.ts" %}
```typescript
import { mergObjects } from '@common-utilities/merge-objects';

mergeObjects({ foo: 'bar' }: unknown, { baz: 'biz' }: unknown); 
```
{% endcode %}



