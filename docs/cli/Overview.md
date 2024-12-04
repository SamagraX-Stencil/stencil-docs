---
title: Overview
---

<head>
  <title>Stencil-Cli Overview</title>
</head>

<p>

## Introduction

The Stencil CLI is a command-line interface tool that helps you to initialize, develop, and maintain your Nest applications. It assists in multiple ways, including scaffolding the project, serving it in development mode, and building and bundling the application for production distribution. It embodies best-practice architectural patterns to encourage well-structured apps.
<br/><br/>
## Installation
**Note**: In this guide we describe using [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) to install packages, including the Stencil-CLI. Other package managers may be used at your discretion.

Install the Stencil-CLI globally using the `npm install -g` command
```
$ npm install -g @samagra-x/stencil-cli
```
### USAGE

The alias for the `nest-cli` has been changed to `stencil`. So, all the commands available with the `nest-cli` are available.
<br/><br/>

## Basic Workflow

Once installed, you can invoke CLI commands directly from your OS command line through the `stencil` executable. See the available `stencil` commands by entering the following:

```bash
$ stencil --help
```
> info **Hint** You can also simply use `stencil` to view the available commands.

Get help on an individual command using the following construct. Substitute any command, like `new`, `add`, etc., where you see `generate` in the example below to get detailed help on that command:

```bash
$ stencil generate --help
```
### Bootstrap a new project

To create a new basic Stencil project in development mode, go to the folder that should be the parent of your new project, and run the following commands:

```bash
$ stencil new app-name
$ cd app-name
$ npm run start
```
##### Options available while bootstrapping a project

In addition to the standard options included, the extra options available are:
- `prisma` : This is a required option with yes/no as acceptable options.
- `user-service` : This is a required option with yes/no as acceptable options.
- `monitoring` : This is a required option with yes/no as acceptable options.
- `monitoring-services` : This is a required option with yes/no as acceptable options.
- `temporal` : This is a required option with yes/no as acceptable options.
- `logging` : This is a required option with yes/no as acceptable options.
- `file-upload` : This is a required option with yes/no as acceptable options.
- `package-manager` : This is a required option with npm/yarn/pnpm/bun as acceptable options.
<br/><br/>
## CLI Command Syntax
All `stencil` commands follow the same format:

```bash
stencil commandOrAlias requiredArg [optionalArg] [options]
```

For example:

```bash
$ stencil new app-name --dry-run
```

Here, `new` is the _commandOrAlias_. The `new` command has an alias of `n`. `app-name` is the _requiredArg_. If a _requiredArg_ is not supplied on the command line, `stencil` will prompt for it. Also, `--dry-run` has an equivalent short-hand form `-d`. With this in mind, the following command is the equivalent of the above:

```bash
$ stencil n app-name -d
```

Most commands, and some options, have aliases. Try running `stencil new --help` to see these options and aliases, and to confirm your understanding of the above constructs.

</p>