---
title: Setting Up File Upload
sidebar_label: File Upload Setup
---

<head>
    <title>File Upload Setup</title>
</head>
<p>

If you forgot to initialize `service-file-upload` when creating your new Stencil app, you can still add it using the following command:

```sh
stencil g service-file-upload
# or 
stencil g fu
```

This command installs all necessary dependencies for `service-file-upload`.

**Note:** For better safety, execute:
```sh
npm install
or
yarn install
```

## Setup Dependent Services

This example depends on MinIO as an S3-based storage engine to store the uploaded files. A `docker-compose.yml` file has been provided at the root of this project which sets up a Minio instance for your use. You can start the instance by running:

```bash
docker-compose up -d
```

## Setting up the Environment

Copy the example environment file to create your own `.env` file:

```bash
cp env-example .env
```

## Setting up File Upload Manually

To manually set up the `file-upload` functionality, you need to register the `FileUploadModule` module in your module which can be imported from the `@samagra-x/stencil` package.

**Prerequisites:**
```sh
npm i @samagra-x/stencil
```

For example:
```typescript
// other imports 
import { FileUploadModule } from '@samagra-x/stencil';

@Module({
  imports: [FileUploadModule],
  // other configs
})
export class AppModule {}
```

> Via the [CLI](https://github.com/SamagraX-stencil/stencil-cli)

To set up `file-upload` functionality automatically via the CLI, simply run the following command:

```bash
stencil add service-file-upload 
```

## Running the App

```bash
# development
yarn run start
# or
npm run start

# watch mode
yarn run start:dev
# or
npm run start:dev

# production mode
yarn run start:prod
# or
npm run start:prod
```

## Test

```bash
# unit tests
yarn run test
# or
npm run test

# e2e tests
yarn run test:e2e
# or
npm run test:e2e

# test coverage
yarn run test:cov
# or 
npm run test:cov
```

## File Upload Instructions

To upload single or multiple files, follow the steps below:

### Endpoint
`POST /files/upload-files`

### Query Parameters
- **destination**: Specifies the target directory for the uploaded files. Example: `/files/upload-files?destination=uploads`.

### Request Body
The request should include the following form-data fields:
- **file**: The file(s) to be uploaded.
- **filename**: The corresponding filename(s) for the uploaded file(s).

**Note**: Ensure that the number of files and filenames are the same and listed in the correct order.

### Example
To upload files to the `uploads` directory:
```
POST /files/upload-files?destination=uploads
```
In the form-data:
- Add the files under the field name `file`.
- Add the filenames under the field name `filename`.

## File Download Instructions

To download a file, follow the steps below:

### Endpoint
`GET /files/download/:destination`

### Parameters
- **destination**: The relative path to the file within the `uploads` directory. For example, if the file is located at `your_project/uploads/resume`.

### Example
To download a file located at `your_project/uploads/resume`:
```
GET /files/download/resume
```

**Note**: The default base directory for downloads is `/uploads`, located at the root level of your project directory (same level as the `node_modules` directory).

By following these steps, you can efficiently handle file uploads and downloads within your project.
</p>