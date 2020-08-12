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
