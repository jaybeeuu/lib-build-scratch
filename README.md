# Library Build Notes

## semantic-ui-react

- [Docs](https://react.semantic-ui.com/)
- [Github](https://react.semantic-ui.com/)

### Import

```ts
import 'semantic-ui-css/semantic.min.css'
import { Button } from 'semantic-ui-react'
```

### Source

- JS
- Manual ./index.d.ts
- Manual *.d.ts next to files.
- Styles - ? - separate pacakage min.css

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

## material-ui

- [Docs](https://material-ui.com/)
- [Github](https://github.com/mui-org/material-ui/)

### Import

```ts
import Button from '@material-ui/core/Button';
```

(Styles are CSS in JS)

### Source

- JS
- Manual ./index.d.ts
- Manual *.d.ts next to files.
- Styles - CSS in JS via [@material-ui/styles](https://material-ui.com/styles/basics/)

### Package

- JS
  - UMD
    - Bundle
  - ES
    - `// modern build`
    - Lots of files
    - ESNext
  - ESM
    - `// legacy build using ES6 modules`
    - Lots of files
    - ES2015
  - CommonJS
    - `// legacy build using commonJS modules`
    - Lots of files

- Typings
  - Manual ./index.d.ts
  - Manual *.d.ts next to cjs files.

- CSS
  - Separate package

```json
{
  "main": "./index.js",
  "module": "./esm/index.js",
  "typings": "./index.d.ts",
  "sideEffects": false,
}
```

### Build

- npm script -> home grown cli tools.
- [Copy package.json etc.](https://github.com/mui-org/material-ui/blob/next/scripts/copy-files.js) to build dir and publish from there.

- JS
  - UMD
    - Rollup
  - ESM
    - Babel
  - ES
    - Babel
  - CommonJS
    - Babel

- Typings
  - TSC & copied to build dir

- Styles
  - CSS in JS

## React Toolbox

- [Docs](http://react-toolbox.io/#/)
- [Github](https://github.com/react-toolbox/react-toolbox/)

### Import

```ts
import {Button, IconButton} from 'react-toolbox/lib/button';
```

### Source

- JS
- Manual ./index.d.ts
- Manual *.d.ts next to files.
- CSS/Sass Modules - user is [expected to compile](http://react-toolbox.io/#/install)

### Package

- JS
  - ES
    - Source files
  - CommonJS
    - Lots of files

- Typings
  - Manual ./index.d.ts
  - Manual *.d.ts next to cjs and es files.

- CSS
  - CSS/Sass modules by es
  - Compiled modules by CJS - lots of repeated styles.

```json
{
  "main": "./lib",
  "module": "./components",
}
```

### Build

Gulp scripts

- JS
  - ES
    - Babel
  - CommonJS
    - Babel

- Typings
  - copied to lib dir

- Styles
  - PostCSS

## Reactstrap

- [Docs](https://reactstrap.github.io/)
- [Github](https://github.com/reactstrap/reactstrap)

### Import

```ts
import { Button } from 'reactstrap';
```

### Source

- JS
- (Bootstrap)

### Package

- JS
  - Bundles
    - UMD
    - ES
    - CJS
  - ES
    - Source
  - ESM
    - ES2015
  - CommonJS
    - Lots of files

- Typings
  - @types

```json
{
  "main": "lib/index.js",
  "jsnext:main": "es/index.js",
  "module": "es/index.js",
  "jsdelivr": "dist/reactstrap.min.js",
  "unpkg": "dist/reactstrap.min.js",
  "cdn": "dist/reactstrap.min.js",
  "esnext": "src/index.js",
  "sideEffects": false,
  "files": [
    "LICENSE",
    "README.md",
    "CHANGELOG.md",
    "lib",
    "dist",
    "src",
    "es"
  ]
}
```

### Build

- npm script

- JS
  - Bundles
    - Rollup
  - ESM
    - Babel
  - CommonJS
    - Babel