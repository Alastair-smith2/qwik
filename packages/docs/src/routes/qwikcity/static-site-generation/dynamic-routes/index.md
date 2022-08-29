---
title: Dynamic Static Site Generated Routes
---

# Dynamic SSG Routes

```typescript
import type { StaticGenerateHandler } from '@builder.io/qwik-city';

export default component$(() => {
  const { params } = useLocation();

  return <div>Example: {params.id}</div>;
});

export const onStaticGenerate: StaticGenerateHandler = () => {
  const ids = [...]; // id data load implementation

  return {
    params: ids.map((id) => {
      return { id };
    }),
  };
};
```