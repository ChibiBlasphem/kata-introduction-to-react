---
layout: two-cols
---

::title::

# `data` → `useState`

::default::

```tsx
<template>
    <span>{{ myData }}</span>
</template>

<script lang="ts">
export default {
    data() {
        return {
            myData: ''
        };
    }
}
</script>
```

::right::

```tsx
export function MyComponent() {
    const [myData, setMyData] = useState('');

    return <span>{myData}</span>
}
```