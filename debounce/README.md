# Debounce

##### Create a new file <span style='color:red;'> ./src/utils/debounce.tsx </span>

```tsx
export function debounce(fn: (...args: unknown[]) => void, delay: number) {
  const timeoutRef = React.useRef(null);

  function debouncedFn(...args: unknown[]) {
    window.clearTimeout(timeoutRef.current);

    timeoutRef.current = window.setTimeout(() => {
      fn(...args);
    }, delay);
  }

  return debouncedFn;
}
```

##### use debounce on your function or states like searcher

```tsx
import { useState } from 'react'

export default function Users() {
	const [search, setSearch] = useState('')
	const debouncedChange = useDebounce(setSearch, 500)

	return (
		<input type='text' onChange={e => debouncedChange(e.target.value)} />
		...
	)
}
```

##### Using module [interfaces](https://github.com/LeandroGCruzP/docs/tree/main/interfaces) and acknowledgment of [filters](https://github.com/LeandroGCruzP/docs/tree/main/Filters)

### Debounce

##### Debouncing is a programming pattern or a technique to restrict the calling of a time-consuming function frequently, by delaying the execution of the function until a specified time to avoid unnecessary CPU cycles, and API calls and improve performance.
