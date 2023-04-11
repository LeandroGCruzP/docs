# Persistent Layout

First create Layout like
```tsx
interface LayoutProps {
	children: React.ReactNode
}

export default function Layout({ children }: LayoutProps) {
	return (
		<div>
			<header>
				<h1>Header</h1>
			</header>			

			<main>
				{children}
			</main>

			<footer>
	      <h1>Footer</h1>
      </footer>
		</div>
	)
}
```

To use persistent layout, you must create a type in ./src/pages/_app.tsx and create a validation if the PageLayout exists or not. Both cases render different results with PageLayout or without PageLayout
```tsx
import { NextComponentType, NextPageContext } from 'next'
import type { AppProps } from 'next/app'

type ComponentWithPageLayout = AppProps & {
  Component: AppProps['Component'] & {
    PageLayout?: NextComponentType<NextPageContext, any, any>
  }
}

function MyApp({ Component, pageProps }: ComponentWithPageLayout) {
  return (
	  {Component.PageLayout ? (
	    <Component.PageLayout>
	      <Component {...pageProps} />
      </Component.PageLayout>
    ) : (
			<Component {...pageProps} />
    )}
  )
}
```

To render the page with layout you need to declare a property on the page called PageLayout passing the component Layout you want to render
```tsx
import { Layouts } from '../layout'

Home.PageLayout = Layouts.Layout

export default function Home() {
	return (
		<h1>Home</h1>
	)
}
```
