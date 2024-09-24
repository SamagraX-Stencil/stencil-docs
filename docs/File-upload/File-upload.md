---
Title: File Upload
sidebar_label: File Upload
---

<head>
    <title>File Upload</title>
</head>
<p>



## Introduction
The Stencil File Upload module provides a robust and configurable solution for handling file uploads within your application. Built on top of the `multer` middleware for Express, it facilitates the handling of data posted in the `multipart/form-data` format, which is predominantly used for file uploads via HTTP `POST` requests. This module's flexibility allows you to tailor its behavior to suit your specific application requirements.

## Features

### File Upload
The Stencil File Upload module supports both single and multiple file uploads, offering a seamless experience for attaching files through an API `POST` request. Key features include:

- **Multiple File Uploads:** Stencil File upload module supports one or more files in a single request.
- **Storage Options:** Files can be stored in local storage or in a MinIO database, providing flexibility in how you manage and access uploaded files.
- **Configurable Middleware:** Built on `multer`, the module can be adjusted to meet various needs, such as file size limits, file type restrictions, and more.

### File Download
In addition to handling uploads, the Stencil File Upload module includes a comprehensive file download service. This feature ensures that users can reliably retrieve uploaded files as needed. Key features include:

- **Efficient File Retrieval:** Download files with ease.
- **Storage Integration:** Files stored in both local storage and MinIO databases are supported, ensuring that downloads are flexible and accessible regardless of where the files are saved.


**Note:** For additional information on NestJS File Upload, refer to the official NestJS documentation [here](https://docs.nestjs.com/techniques/file-upload)


## Development Setup
To get started with the Stencil File Upload module in your project, initialize a new Stencil project with the file upload service using the following commands in your CLI:

```sh
stencil new <project-name> --service-file-upload 
# or 
stencil new <project-name> -fu
```

This will configure the file upload service in your project, enabling efficient management of file uploads and downloads.

</p>