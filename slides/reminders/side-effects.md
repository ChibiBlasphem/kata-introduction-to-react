---
layout: two-cols
---

::title::

# `mounted` + `beforeUnmount` → `useEffect`

::default::

```tsx
<template>
    <span>Time elapsed: {{ timeElapsed }}</span>
</template>

<script lang="ts">
export default {
    data() {
        timeElapsed: 0,
        intervalId: undefined;
    },
    mounted() {
        this.intervalId = setInterval(() => {
            this.timeElapsed += 1.0;
        }, 1000);
    },
    beforeUnmount() {
        clearInterval(this.intervalId);
    },
}
</script>
```

::right::

```tsx
export function MyComponent() {
    const [timeElapsed, setTimeElapsed] = useState(0);

    useEffect(() => {
        const intervalId = setInterval(() => {
            setTimeElapsed(current => current + 1.0);
        }, 1000);

        return () => {
            clearInterval(intervalId);
        };
    }, []);

    return <span>Time elapsed: {timeElapsed}</span>;
}
```