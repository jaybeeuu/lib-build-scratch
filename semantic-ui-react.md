## semantic-ui-react

- [Docs](https://react.semantic-ui.com/)
- [Github](https://github.com/Semantic-Org/Semantic-UI-React)

### Import

```ts
import 'semantic-ui-css/semantic.min.css'
import { Button } from 'semantic-ui-react'
```

### Source

- JS
- Manual ./index.d.ts
- Manual *.d.ts next to files.
- Styles - [separate pacakage](https://github.com/Semantic-Org/Semantic-UI-CSS) - synced from `less` built out of [here](https://github.com/Semantic-Org/Semantic-UI)?

### Package

- JS
  - UMD
    - Bundle
  - ES
    - ES2015
  - CommonJS
    - Lots of files

- Typings
  - `./index.d.ts`
  - *.d.ts in `dist/commonjs`

- CSS
  - Separate package

```json
{
  "jsnext:main": "dist/es/index.js",
  "main": "dist/commonjs/index.js",
  "module": "dist/es/index.js",
  "types": "index.d.ts",
  "unpkg": "dist/umd/semantic-ui-react.min.js",
  "files": [
    "src",
    "dist",
    "index.d.ts"
  ],
  "sideEffects": false,
}
```
### Build

Gulp tasks

- JS
  - UMD
    - Webpack
  - ES
    - Babel
  - CommonJS
    - Babel

- Typings
  - copy into commonjs dist

- CSS
  - separate package
