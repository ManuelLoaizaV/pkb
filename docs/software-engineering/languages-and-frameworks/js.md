# JavaScript

## Installing nvm

### Script (Linux)

Download and run the following script manually:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

Restart the shell:

```shell
exec $SHELL
```

Verify that `nvm` has been installed:

```shell
command -v nvm
```

### Troubleshooting (macOS)

First, install Xcode command line tools.

Then, run

```shell
touch ~/.zshrc
```

Finally, follow the instructions of the previous section.

## Installing npm and node

To download, compile, and install the latest release of `node`, do this:

```shell
nvm install node
```

## Installing TypeScript

TypeScript is a strongly typed programming language that builds on JavaScript, giving you better tooling at any scale.

```shell
npm install typescript --save-dev
```

Install `ts-node` for TypeScript execution and REPL for node.js, with source map and native ESM support.

```shell
npm install ts-node --save-dev
```

## Useful links

- [What is the difference between `--save` and `--save-dev`?](https://stackoverflow.com/questions/22891211/what-is-the-difference-between-save-and-save-dev)

- [Airbnb JavaScript Style Guide.](https://github.com/airbnb/javascript)