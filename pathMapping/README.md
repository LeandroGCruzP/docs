# Path Mapping

Add compiles options on ```./tsconfig.json```
```json
{
  "compilerOptions": {
    //...
    "baseUrl": "./",
    "paths": {
      "~/*": ["src/*"],
    }
  }
}
```

To use path mapping of component Button
```tsx
import { Shares } from '~/shares'

export default function Home() {
	return (
		<Shares.Button />
	)
}
```
