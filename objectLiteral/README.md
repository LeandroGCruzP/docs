# Object Literal

##### Before

```tsx
type State = 'first' | 'second' | 'third'
type Data = {...}

function Page () {
	const [state, setState] = useState<State>()

	const data: Data = {...}

	useEffect(() => {
		function fn(data: Data) {
			if (state === 'first') {...}
			if (state === 'second') {...}
			if (state === 'third') {...}
		}

		fn(data)
	}, [state])

	return ...
}
```

##### After

```tsx
type State = 'first' | 'second' | 'third'
type Data = {...}

export default function Page () {
	const [state, setState] = useState<State>()

	const data: Data = {...}

	useEffect(() => {
		const collectionFn = {
			first(data: Data) {...},
			second(data: Data) {...},
			third(data: Data) {...},
		}

		const fn = collectionFn[state]
		fn(data)
	}, [state])

	return ...
}
```

### Object Literal

##### An object literal is a comma-separated list of name-value pairs inside of curly braces. Those values can be properties and functions.
