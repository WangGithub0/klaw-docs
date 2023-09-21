# Klaw documentation

- Please be aware of our [Code of Conduct](/CODE_OF_CONDUCT.md) ❤️

## About

This is the Klaw documentation repository. Welcome 👋 🎉
You can find source code and all content for our ([klaw-project.io](https://www.klaw-project.io/) site here.

## Installation and usage

### Requirements

- [node](https://nodejs.org/en/) needs to be installed.
  -> please check [nvmrc](.nvmrc) or the `engines` definition in [package.json](package.json) for version.

This is the setup you every time. You can find the different ways how to run the local development process below.

### Local development

Install all needed dependencies and setup githooks:

```shell
npm install
```

To start local the local development server, run:

```shell
npm start
```

## Scripts used and what they execute

ℹ️ You can see all our scripts in the [`package.json`](package.json).
You can also run `npm run` in your console to get a list of all available scripts.

Here are the important ones you're likely to use:

- `npm start`: starts the app for development
- `npm run build`: will build the documentation site and generate all static files in "build". After `build` you can
  run `npm run serve` to test your build locally
- `lint`: runs a format check and if no error is found, lints code and markdown files in the project.
  - the linting script does not mutate your code. See [Linting and code formatting](#linting-and-code-formatting) for
    more info.
- `reformat`: runs the code formatter (prettier) as well as the markdown linter in fix mode. This will mutate you code.

ℹ️ We are using a custom hook path for enabling pre-commit hooks. This path is set in the local git config when
running `npm install`.

## Linting and code formatting

How we keep our app's codebase looking consistent and nice 💅🏼

- [Prettier](https://prettier.io/) for code formatting
- [ESlint](https://eslint.org/) and various plugins for linting
- [markdownlint](https://github.com/DavidAnson/markdownlint) in combination
  with [markdownlint-cli](https://github.com/igorshubovych/markdownlint-cli) to check and format markdown files
  specially.

### Fine-grained scripts for linting and formatting

We provide `npm run lint` as well as `npm run reformat` to check or mutate your changes. We also offer more specific
scripts you can use:

Scripts with `lint` do not mutate your code in any way:

- `npm run lint:code` - runs a prettier and eslint check. This includes basic checks for markdown, but not
  in depth.
- `npm run lint:markdown` - runs markdown-lint with more detailed check on markdown files.

To apply findings from `lint` and mutate your files:

- `npm run reformat:code` - runs prettier and eslint in fix mode.
- `npm run reformat:markdown` - runs markdownlint in fix mode.

ℹ️ It's convenient to let prettier and eslint auto-format your code "on save" by your IDE or editor. For markdownlint
you can find [plugins for some IDE/editors](https://github.com/DavidAnson/markdownlint#related), too.