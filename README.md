# `stringifyStatic` renders `:disabled="0"` as a present attribute

Minimal Vite + Vue 3.5.44 reproduction.

The [boolean attributes](https://vuejs.org/guide/essentials/template-syntax.html#boolean-attributes) docs say a falsy value such as `0` omits the attribute. `Save` follows that. `Save article` does not: its surrounding static tree is stringified to `<button disabled="0">`, and the browser treats that attribute as present.

The SFC Playground cannot show this. Its compiler runs in the browser, where `stringifyStatic` is disabled.

```sh
npm install
npm run dev
npm run build
```

The production bundle contains `disabled="0"` for the article button only.
