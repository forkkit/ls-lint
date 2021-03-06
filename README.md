# ls-lint

An extremely fast file and directory name linter

[![Build Status](http://ci.loeffel.io/api/badges/loeffel-io/ls-lint/status.svg)](http://ci.loeffel.io/loeffel-io/ls-lint)
[![Go Report Card](https://goreportcard.com/badge/github.com/loeffel-io/ls-lint)](https://goreportcard.com/report/github.com/loeffel-io/ls-lint)

- Works for directory and file names (all extensions supported)
- Linux, MacOS & Windows Support
- Incredibly fast
- Full unicode support
- Almost zero third-party dependencies (only [go-yaml](https://github.com/go-yaml/yaml))

## Demo

<img src="https://i.imgur.com/plZml7D.gif" alt="command" width="600">

## Example & How-to ([vue.js](https://github.com/vuejs/vue))

- `.ls-lint.yml` file must be present in your root directory
- Multiple rules supported by `,`
- `.dir` set rules for the current directory and their subdirectories
- Rules for subdirectories will overwrite the rules for all their subdirectories
- For Windows you must use backslashs `\` instead of slashs `/` 

```yaml
# .ls-lint.yml

ls:
  .dir: kebab-case
  .js: kebab-case
  .css: kebab-case
  .html: kebab-case
  .json: kebab-case
  .ts: point.case
  .sh: kebab-case

  dist:
    .dir: kebab-case
    .js: point.case

  packages/vue-server-renderer:
    .dir: kebab-case
    .js: point.case
    .json: kebab-case

  types/test:
    .dir: kebab-case
    .js: kebab-case
    .json: kebab-case

ignore:
  - .babelrc.js
  - .eslintrc.js
  - .github
  - .circleci
  - .git
  - benchmarks
  - test
```

## Install & Run

## Binary

### MacOS

```bash
curl -sL -o ls-lint https://github.com/loeffel-io/ls-lint/releases/download/v1.1.0/ls-lint-darwin && chmod +x ls-lint && ./ls-lint
```

### Linux

```bash
curl -sL -o ls-lint https://github.com/loeffel-io/ls-lint/releases/download/v1.1.0/ls-lint-linux && chmod +x ls-lint && ./ls-lint
```

### Windows

```bash
# (!) First download the .exe from https://github.com/loeffel-io/ls-lint/releases/download/v1.1.0/ls-lint-windows.exe
ls-lint-windows.exe
```

## NPM

### Install

```bash
# global
npm install -g ls-lint-linux # for Linux
npm install -g ls-lint-darwin # for macOS

# local
npm install ls-lint-linux # for Linux
npm install ls-lint-darwin # for macOS
```

### Run

```bash
# global
ls-lint

# local
node_modules/.bin/ls-lint
npx ls-lint
```

## Rules

| Rule       | Alias       | Description                                                    |
| ---------- | ----------- | -------------------------------------------------------------- |
| lowercase  | -           | Checks if every letter is lower; Skip non letters              |
| camelcase  | camelCase   | Checks if string is camel case; Only letters allowed           |
| pascalcase | PascalCase  | Checks if string is pascal case; Only letters allowed          |
| snakecase  | snake_case  | Checks if string is snake case; Only letters and `_` allowed   |
| kebabcase  | kebab-case  | Checks if string is kebab case; Only letters and `-` allowed   |
| pointcase  | point.case  | Checks if string is "point case"; Only letters and `.` allowed |

## Roadmap

- [ ] Npm Windows package
- [ ] Color highlighting
- [ ] Regex Rule
- [ ] Docker support
- [x] Windows support
- [x] Npm package
- [x] Add ignore directories and files

## License

ls-lint is open-source software licensed under the MIT license.