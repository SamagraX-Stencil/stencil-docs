---
title: Commands
---

<head>
  <title>Stencil-Cli Commands Setup</title>
</head>
<p>

## Build Command

Compiles an application or workspace into an output folder.

```bash
$ stencil build <name> [options]
```

**Arguments**

| Argument | Description                       |
| -------- | --------------------------------- |
| `<name>` | The name of the project to build. |

**Options**

| Option             | Description                                                                                                                                                                                |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `--path [path]`    | Path to `tsconfig` file. <br/>Alias `-p`                                                                                                                                                   |
| `--config [path]`  | Path to `nest-cli` configuration file. <br/>Alias `-c`                                                                                                                                     |
| `--watch`          | Run in watch mode (live-reload).<br /> If you're using `tsc` for compilation, you can type `rs` to restart the application (when `manualRestart` option is set to `true`). <br/>Alias `-w` |
| `--builder [name]` | Specify the builder to use for compilation (`tsc`, `swc`, or `webpack`). <br/>Alias `-b`                                                                                                   |
| `--webpack`        | Use webpack for compilation (deprecated: use `--builder webpack` instead).                                                                                                                 |
| `--webpackPath`    | Path to webpack configuration.                                                                                                                                                             |
| `--tsc`            | Force use `tsc` for compilation.                                                                                                                                                           |
## Start Command

Compiles and runs an application (or default project in a workspace).

```bash
$ stencil start <name> [options]
```

**Arguments**

| Argument | Description                     |
| -------- | ------------------------------- |
| `<name>` | The name of the project to run. |

**Options**

| Option                  | Description                                                                                                          |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `--path [path]`         | Path to `tsconfig` file. <br/>Alias `-p`                                                                             |
| `--config [path]`       | Path to `nest-cli` configuration file. <br/>Alias `-c`                                                               |
| `--watch`               | Run in watch mode (live-reload) <br/>Alias `-w`                                                                      |
| `--builder [name]`      | Specify the builder to use for compilation (`tsc`, `swc`, or `webpack`). <br/>Alias `-b`                             |
| `--preserveWatchOutput` | Keep outdated console output in watch mode instead of clearing the screen. (`tsc` watch mode only)                   |
| `--watchAssets`         | Run in watch mode (live-reload), watching non-TS files (assets). See [Assets](cli/monorepo#assets) for more details. |
| `--debug [hostport]`    | Run in debug mode (with --inspect flag) <br/>Alias `-d`                                                              |
| `--webpack`             | Use webpack for compilation. (deprecated: use `--builder webpack` instead)                                           |
| `--webpackPath`         | Path to webpack configuration.                                                                                       |
| `--tsc`                 | Force use `tsc` for compilation.                                                                                     |
| `--exec [binary]`       | Binary to run (default: `node`). <br/>Alias `-e`                                                                     |
| `-- [key=value]`        | Command-line arguments that can be referenced with `process.argv`.                                                   |

## Add Command

Imports a library that has been packaged as a **nest library**, running its install schematic.

```bash
stencil add <name> [options]
```

**Arguments**

| Argument | Description                        |
| -------- | ---------------------------------- |
| `<name>` | The name of the library to import. |

## Info Command

```
stencil info
```

Displays information about installed stencil packages and other helpful system info. 

## List Command

```
stencil list
```

Consoles a registry/spec file which shows all the installed services along with installed package manager.

## Docker Command

```
stencil docker <services...>
stencil do <services...>
```
**Description**

Creates a docker service/container for given prompt.
-  Tooling specific setup
    - Creates a folder with the given `<service>` inside docker directory
- À la Carte setup
    - Creates a docker compose or updates existing docker compose with desired `<service>`

**Arguments**

| Argument  |  Description |
|-----------|--------------|
|  `<service>`	 | The name of the new project |

Note: Docker command supports multiple services at a time.

**Services**

-  Tooling specific setup


| Name  | Alias  |  Description |
|---|---|---|
|  `logging` | `lg`  | Generates a docker service for logging |
|  `monitoringService` |`ms`   | Generates a docker service for monitoring  |
|  `temporal` |  `tp` |  Generates a docker service for temporal |

- À la Carte setup


| Name  | Alias  |  Description |
|---|---|---|
|  `postgres` | `pg`  | Generate a docker compose for postgres |
|  `hasura` |`hs`   | Generate a docker compose for hasura  |


## Generate Command


```
stencil generate <schematic> <name> [options]

stencil g <schematic> <name> [options]
```
**Description**

Generates and/or modifies files based on a schematic

**Arguments**

| Argument  |  Description |
|-----------|--------------|
|  `<service>`	 | The schematic or collection:schematic to generate. See the table below for the available schematics. |
|  `<name>`	 | The name of the new project |

**Schematics**

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


**Options**

| Option                          | Alias | Description                                                                                                     |
| ------------------------------- | ----- | --------------------------------------------------------------------------------------------------------------- |
| `--dry-run`                     | `-d`  | Reports changes that would be made, but does not change the filesystem.                                        |
| `--project [project]`           | `-p`  | Project that element should be added to.                                                                       |
| `--flat`                        |   | Do not generate a folder for the element.                                                                       |
| `--collection [collectionName]` | `-c`  | Specify schematics collection. Use package name of installed npm package containing schematic.                |
| `--spec`                        |   | Enforce spec files generation (default)                                                                         |
| `--no-spec`                     |    | Disable spec files generation                                                                                   |



</p>