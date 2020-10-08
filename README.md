[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg)](https://conventionalcommits.org)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Intro

Template that can be used for working with monorepositories in typescript / javascript and automated changelog generation.
Solves problems like versioning, publishing, dependencies between packages, developing both the depending and dependant packages at the same time, building/installing all packages dependencies with one command, besides having the benefits of typescript and definition files..

## How to create a new package

1. `lerna create <package-name>`
1. create a `src/index.ts` file
1. copy `tsconfig.json` from one of the other files which extends the root tsconfig file
1. add `"typings": "lib/index.d.ts"` in package.json to link to the generated .d.ts file for types reference
1. Make sure the `main` property is set to the output `lib/index.js` file in `package.json`
1. add `build` and `watch` scripts in package.json

## Starting the project

1. Use `yarn build` or `yarn watch` to compile all packages into javascript and optionally recompile on file changes
2. Use `yarn start` to run the main project or the playground which uses the shared packages

## Publishing / Releasing

1. run `yarn publish`
