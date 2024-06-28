---
title: Scripts
---

<head>
  <title>Stencil-Cli Introduction</title>
</head>
<p>

## Stencil CLI and Scripts

This section provides additional background on how to use npm scripts to manage the build and execution process of a Stencil application.

A Stencil application is a **standard** TypeScript application that needs to be compiled to JavaScript before it can be executed. There are various ways to accomplish the compilation step, and developers/teams are free to choose a way that works best for them. With that in mind, Stencil provides a set of tools out-of-the-box that seek to do the following:

This goal is accomplished through a combination of a locally installed TypeScript compiler and `package.json` scripts. We describe how these technologies work together below. This should help you understand what's happening at each step of the build/execute process, and how to customize that behavior if necessary.

### Linking

To link a local package, use the following npm command:

```bash
$ npm link
```

This is useful when you are developing multiple packages locally and want to test them together.

### Build

You can build your Stencil application using the following npm command:

#### **Note : make sure to keep dependencies in-check and update the required packages**

```bash
$ npm run build
```

This command will compile the TypeScript code to JavaScript, ensuring that the application is ready to be executed.

### Execution

To start your Stencil application, use the following npm command:

```bash
$ npm run start
```

This command will execute the compiled application.

#### Package Scripts

Running the above commands at the OS command level ensures that the build and execute processes are managed as project dependencies in `package.json`. This way, all members of your organization can be assured of running the same version of the commands. By following this **recommended** usage, you can fully customize the behavior of these scripts via their options and/or customize the `tsc` compiler options files (e.g., `tsconfig.json`) as needed.

For most developers/teams, it is recommended to utilize the package scripts for building and executing their Nest projects.</p>