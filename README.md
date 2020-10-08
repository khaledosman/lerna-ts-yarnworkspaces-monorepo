[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg)](https://conventionalcommits.org)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Intro
Template that can be used for working with monorepositories in typescript / javascript and automated changelog generation.
Solves problems like versioning, publishing, dependencies between packages, developing both the depending and dependant packages at the same time, building/installing all packages dependencies with one command, besides having the benefits of typescript and definition files..

## DEMO
<figure class="video_container">
  <iframe src="https://drive.google.com/file/d/1x6R1AQhA3G4fMBbIoS_0kcGVOIJJnsLe/preview" frameborder="0" allowfullscreen="true"> </iframe>
</figure>

## Adding a new package
1. `lerna create ${packageName}`
1. create a `src/index.ts` file
1. add `tsc` and `watch` to scripts in package.json
2. copy `tsconfig.json` from one of the other files which extends the root tsconfig file
3. add `"typings": "lib/index.d.ts"` in package.json to link to the generated .d.ts file for types reference
4. to build all packages simply run `lerna run tsc` or in development mode to rebuild when any of the dependent packages updates `lerna run watch`
5. You can import shared packages by their name in package.json, its a best practice to use npm scopes in package names.. i.e (@namespace/serviceA)
6. run the playground / main app with nodemon `yarn start`, now if you change any of the packages and restart the app you'll automatically see the new version

## Usage
1. Run `lerna bootstrap` to link all packages and install their dependencies
2. Run `lerna run tsc` to compile typescript into javascript for all packages so you can import the generated js and .d.ts in your code
