## Adding a new package
1. `lerna create ${packageName}`
1. create a `src/index.ts` file
1. add `tsc` to scripts in package.json
2. add watch script to package.json to automatically rebuild dist files on src file changes `"watch": "tsc --watch"` so you can automatically reuse the built js files in depending services
3. copy `tsconfig.json` from one of the other files which extends the root tsconfig file
4. add "typings": "lib/index.d.ts" in package.json to link to the generated .d.ts file
5. to build all packages simply run `lerna run tsc`
6. You can import shared packages by their name in package.json, its a best practice to use npm scopes in package names.. i.e (@namespace/serviceA)

## Usage
1. Run `lerna bootstrap` to link all packages and install their dependencies
2. Run `lerna run tsc` to compile typescript into javascript for all packages so you can import the generated js and .d.ts in your code
