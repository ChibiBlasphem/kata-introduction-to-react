# Conventions

- All components reside in `src/components` folder
- Each component has its own folder, for example:  
  ```shell
  MyComponent                   # Component folder
  ├── components                # If `MyComponent` has sub components
  │   └── SubComponent
  ├── MyComponent.tsx           # Component file
  ├── MyComponent.stories.tsx   # Storybook stories file
  ├── MyComponent.styles.ts     # Styled components
  ├── MyComponent.test.ts       # Unit tests
  ├── MyComponent.types.ts      # Public interfaces, enums, types
  └── MyComponent.hooks.ts      # Custom hooks used by your component
  ```
- Component props should be named `{ComponentName}Props` (ex: `MyComponentProps`)
- Styled components should be named `{ComponentName}{Element}` (ex: `MyComponentTitle`)
- Always use named exports (ex: `export function MyComponent() { /* ... */ }`)