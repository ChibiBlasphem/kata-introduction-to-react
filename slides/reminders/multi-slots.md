---
layout: two-cols
---

::title::

# Multi slots → Props

::default::

Component:

```tsx
<template>
  <div class="container">
    <div class="title">
      <slot />
    </div>
    <div class="details">
      <slot name="details" />
    </div>
  </div>
</template>
```

Usage:

```tsx
<template>
  <MyComponent>
    <template v-slot:default>
      My title
    </template>
    <template v-slot:details>
      <span>My details</span>
    </template>
  </MyComponent>
</template>
```

::right::

Component:

```tsx
import type { ReactNode } from 'react';

interface MyComponentProps {
  children: ReactNode;
  details: ReactNode;
}

export function MyComponent({ details, children }: MyComponentProps) {
  return (
    <div className="container">
      <div className="title">
        {children}
      </div>
      <div className="details">
        {details}
      </div>
    </div>
  )
}
```

Usage:

```tsx
<MyComponent details={<span>My details</span>}>
  My title
</MyComponent>
```