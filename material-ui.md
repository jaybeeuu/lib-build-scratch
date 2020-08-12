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
