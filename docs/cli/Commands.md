---
Title: CLI command reference
sidebar_label: CLI command reference
---

<head>
  <title>Stencil-Cli Commands Setup</title>
</head>
<p>

### Stencil `New`
Creates a new (standard mode) Stencil project.
```
$ stencil new `<name>` [option]
# or 
$ stencil n `<name>` [option]
```

**Description**
Creates and initializes a new `Stencil` project. Prompts for package manager.
- Creates a folder with the given `<name>`.
- Populates the folder with configuration files
- Creates sub-folders for source code `(/src)` and end-to-end tests `(/test)`
- Populates the sub-folders with default files for app components and tests

**Arguments**

| Argument | Description                  |
|----------|------------------------------|
| `<name>` | The name of the project to build.  |

### Stencil `info` 

The `info` command provides detailed information about your current stencil project, including dependencies, versions, and configuration settings.

**Usage:**

```sh
$ stencil info
```
### Stencil `generate`

The `generate` command helps you generate various stencil components such as modules, controllers, services, and more.

**Usage:**

```sh
Stencil generate <schematic> <name> [path]
# or
Stencil g <schematic> <name> [path]
```
**Arguments**

| Argument     | Description                                                                                     |
|--------------|-------------------------------------------------------------------------------------------------|
| `<schematic>`| The schematic or collection:schematic to generate. |
| `<name>`     | The name of the generated component.     

### Stencl Build
Compiles an application or workspace into an output folder. 

**Note:** Also, the `build` command is responsible for mapping paths.

```sh
$ stencil build <name>
```

| Argument | Description                  |
|----------|------------------------------|
| `<name>` | The name of the project to build.  |

### Stencil `add`

The `add` command is used to add new dependencies and integrations to your stencil project. This is typically used for adding third-party libraries.

**Usage:**

```sh
$ Stencil add <library>
```

### Stencil `start`

The `start` command starts the stencil application. It runs the server and makes your application available.

**Usage:**

```sh
$ stencil start
```
### Stencil `list`

The `list` command lists all the available schematics and commands that you can use with the stencil CLI.

**Usage:**

```sh
$ stencil list
```
### Stencil `docker`

The `docker` command integrates Docker support into your stencil project, allowing you to containerize your application easily.

**Usage:**

```sh
$ stencil docker
```

## New command
The Stencil `new` command is used to create and initialise a new Stencil project.

```
$ stencil new <name> [option]
# or 
$ stencil n <name> [option]
```

**Available Options:**

1.**prisma** : This is a required option with yes/no as acceptable options.

2.**user-service** : This is a required option with yes/no as acceptable options.

3.**monitoring** : This is a required option with yes/no as acceptable options.

4.**temporal** : This is a required option with yes/no as acceptable options.

5.**logging** : This is a required option with yes/no as acceptable options.

6.**file-upload** : This is a required option with yes/no as acceptable options.

7.**package-manager** : This is a required option with npm/yarn/pnpm/bun as acceptable options.

**Flags:** 
You can even choose the services that you want your application to have using the options or you can attach `Flags` to your Stencil new command.
```sh
$ stencil new <name> --flagname
# or
$ stencil new <name> -flagalias
```
**For Example:**
```sh
$ stencil new my-app --monitoring 
# or 
$ stencil new my-app -mf
```
**Note:** The default value of a service when attached as a flag is considered to be as `yes`.

**List of Services**

| Name  | Alias  |  Description |
|---|---|---|
|  `app` |   | Generate a new application within a monorepo (converting to monorepo if it's a standard structure). |
|  `library` |`lib`   | Generate a new library within a monorepo (converting to monorepo if it's a standard structure).  |
|  `class` |`cl`   | Generate a new class.|
|  `controller` |`co`   | 				Generate a controller declaration.|
|  `decorator` |`d`   |  Generate a custom decorator. |
|  `filter` |`f`   | Generate a filter declaration.  |
|  `gateway` |`ga`   | Generate a gateway declaration.  |
|  `guard` |`gu`   |  Generate a guard declaration. |
|  `interface` |`itf`   | Generate an interface.  |
|  `interceptor` |`itc`   |  Generate an interceptor declaration. |
|  `middleware` |`mi`   | Generate a middleware declaration.  |
|  `module` |`mo`   | Generate a module declaration.  |
|  `pipe` |`pi`   |  Generate a pipe declaration. |
|  `provider` |`pr`   | Generate a provider declaration.  |
|  `resolver` |`r`   | Generate a resolver declaration.  |
|  `resource` |`res`   | Generate a new CRUD resource. See the CRUD (resource) generator for more details. (TS only)  |
|  `service` |`s`   |  		Generate a service declaration.|
|  `sub-app` |`app`   |  Generate a new application within a monorepo |
|  `service-prisma` |`sp`   | Generate the Prisma service file  |
|  `service-user` |`su`   |  Add the User Service module from the package. |
|  `fixtures` |`fs`   |  Generate Custom Fixtures Files. |
|  `husky` |`hs`   | Generate Custom husky Files.  |
|  `github` |`gh`   | Generate Custom github Files.  |
|  `prisma` |`ps`   |  Add custom prisma models to the schema.prisma file. |
|  `devcontainer` |`dc`   |  Generate files in a .devcontainer file |
|  `monitoring` |`mf`   |  Generate monitor folder. |
|  `service-temporal` |`te`   | If you want to have temporal setup in the project.  |
|  `service-file-upload` |`fu`   | If you want to have fileUpload setup in the project.  |
</p>