Using React/Typescript/Styled-components, when we have a Theme type defined as follow:

```ts
export const theme {
  grey: 'grey'
}
```

We then provide the theme in our app.tsx:

```tsx
<ThemeProvider theme={theme}>
  <>
    <GlobalStyles />
    <Component {...pageProps} />
  </>
</ThemeProvider>
```

We then create a `globalStyles.tsx` file and want to use the theme in it as follow

```tsx
import {createGlobalStyle} from 'styled-components'

const GlobalStyles = createGlobalStyle`
  body {
    background-color: ${({theme}) => theme.grey};
  }
`
```

we get the following error:
`Property 'grey' does not exist on type 'DefaultTheme'`

This can be fixed as follows:
- create a type for your theme:
```ts
export type ThemeType {
  grey: string
}
```

```tsx
import {createGlobalStyle} from 'styled-components'
import {ThemeType} from './theme'

const GlobalStyles = createGlobalStyle<{theme: ThemeType}>`
  body {
    background-color: ${({theme}) => theme.grey};
  }
`
```

But the better way to implement a theme is [in the official docs](https://styled-components.com/docs/api#create-a-declarations-file)
