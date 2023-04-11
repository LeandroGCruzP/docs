# Export all components as const

Create a new component
```tsx
export function Button() {
	return (
		<button>Press</button>
	)
}
```

Create file ```index.ts``` to export all components
```tsx
import { Button } from './Button'

export const Shares = {
	Button
}
```

Using const in another component
```tsx
import { Shares } from '../shares'

export default function Home() {
	return (
		<Shares.Button />
	)
}
```
