# Installation and running this project stub

1. Install `npm` in some way. It is the package manager commonly used with javascript and node.js
2. Call `npm install`. It installs `typescript`, `jest` and `ts-jest`. The details of _what_ gets installed is described in `package.json`.
3. Call `npm test` to run all tests. In `package.json`, this is defined to just call `jest`. Jest is in turn configured by `jest.config.js`. It will compile all typescript files and run tests located in files called `*.test.ts`. See See https://jestjs.io/ for details.
4. Call `npm run lint` to lint the program. It runs eslint with typescript support. The configuration of eslint is specified in `.eslintrc.js` See https://typescript-eslint.io/. for details.
5. It is typically quite nice to get formatting help. Where should all blank spaces go? Newlines? We use `prettier` to help us with that. See https://prettier.io for details. Run `npx prettier --check .` to know where you did some mistake. If you want to get it fixed, you can call `npx prettier --write .`. This command is also available as `npm run format`.
6. If all test pass, and the linting is ok, you might call `npm start`, to start the program. It will compile the program with `tsc` and then run the program using `node`. There is a chance that the typescript compiler will have found some nasty type errors, and in that case, it will tell you.

The file `.gitignore` is to tell git, the version control software, to not track the compiled output files.
You can safely ignore that file and pretend it does not exist.

### Troubleshooting

Running Jest on windows can sometimes be VERY slow. A test that should take 1.5 seconds takes 30 seconds when running on some windows file system. Moving the code to the linux partition of WSL solves the problem.

Jest will also crash mysteriously if your node version is too old. Using a recent version of node should do it.

This project assumes we use CommonJS modules, since that is the "normal" thing to do in typescript node.js applications. Some libraries on npm are not compatible with CommonJS, but only provide ECMAscript modules. One such example is `random`. If you get such problems, simple use another library.

Writing cli apps in plain node.js is not advisable. One could use https://nodejs.org/api/readline.html#readline, but this is a pains since it is callback based, or promises based (will be similar experience to callbacks. equally bad.