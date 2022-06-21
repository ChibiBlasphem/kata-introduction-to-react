---
layout: two-cols
---

::title::

# Theming from outside component

::default::

Component:

```tsx
import styled from 'styled-components';

const ButtonRoot = styled.button`
  color: var(--button-color);
	background-color: var(--button-background-color);
`;

interface ButtonProps { className: string }

export function Button({ className }: ButtonProps) {
	return (
		<ButtonRoot className={className}>
			{/* ... */}
		</ButtonRoot>
	)
}
```

::right::

Usage:

```tsx
import styled from 'styled-components';

const MyThemedButton = styled(Button)`
	--button-color: #fff;
	--button-background-color: #88b2a8;
`;

<MyThemedButton>{/* ... */}</MyThemedButton>
```