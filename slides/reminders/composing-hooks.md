---
layout: two-cols
---

::title::

# Compose your hooks

::default::

`MyComponent.tsx`

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
    }, [])

    return <span>Time elapsed: {timeElapsed}</span>
}
```

::right::

<v-click>

`MyComponent.hooks.ts`

```ts
import { useState, useEffect } from 'react';

export function useTimeElapsed(initialValue: number) {
    const [timeElapsed, setTimeElapsed] = useState(initialValue);

    useEffect(() => {
        const intervalId = setInterval(() => {
            setTimeElapsed(current => current + 1.0);
        }, 1000);

        return () => {
            clearInterval(intervalId);
        };
    }, []);

    return timeElapsed;
}

```

`MyComponent.tsx`

```tsx
import { useTimeElapsed } from './MyComponent.hooks';

export function MyComponent() {
    const timeElapsed = useTimeElapsed(0);
    
    return <span>Time elapsed: {timeElapsed}</span>
}
```

</v-click>