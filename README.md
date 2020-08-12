# Library Build Investigation

This repo is an investigatino in to the build techniques and package content of some react component libraries.

I looked at:

- [material-ui](./material-ui.md)
- [semantic-ui-react](./semantic-ui-react,md)
- [reactstrap](./reactstrap.md)
- [react-toolbox](./react-toolbox.md)

The adhoc and notesy analysis is given in the MD files linked.

There is no runnable code in this repo, but if you wnat to have a look at the package content for each then you can pull this down and install the dependencies. (I used `pnpm` because it leaves a cleaner `node_modules`.)

```sh
pnpm install
```

## TLDR;

> Raw source if JavaScript in stage >= 4.
> Transpiled source if Typescript or any other language.
> There is no specced solution for styles yet, but all tools understand importing css. Transpile it to css if in a different language.
> Best publish a ESM, but CommonJs is fine too. To usage in node.js publish both.
> You can bundle as ESM e. g. via rollup but this breaks/hinders some optimizations like sideEffects-flag or splitChunk, but has benefits for application build time.
> Minimizing is an application-level concern and I wouldn't ship my library minimized. It's also difficult to debug. But it has benefits to application build time.
~ [sokra](https://github.com/webpack/webpack/issues/11277#issuecomment-671086083)

