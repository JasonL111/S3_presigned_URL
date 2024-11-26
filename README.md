# S3 Presigned URL Generator for Backblaze B2

This tool is a Go application that generates presigned URLs for all objects in a specified Backblaze B2 bucket. The presigned URLs allow you to download objects securely and are written to a `presigned_urls.txt` file.

## Features

- **Generate Presigned URLs**: Creates presigned URLs for all objects or objects with a specific prefix in a Backblaze B2 bucket.
- **Customizable URL Expiration**: Set the expiration time for the presigned URLs.
- **Environment Configuration**: Uses a `.env` file to manage configuration and credentials securely.
- **Support for Object Prefixes**: Optionally generate URLs for objects with a specific prefix.

## Prerequisites

- **Go Language**: You need to have Go installed (version 1.16 or higher recommended).
- **Backblaze B2 Account**: A Backblaze B2 account with an application key and key ID.

## Installation

1. **Clone the Repository**:
`git clone https://github.com/yourusername/your-repo-name.git`
`cd your-repo-name`

### Install dependencies
`go mod tidy`


## Usage
1. **Prepare the .env file: Create a .env file in the root directory of the project. Example:**:
    ```bash
    B2_KEY_ID=your-key-id
    B2_APPLICATION_KEY=your-application-key
    B2_ENDPOINT=endpoint
    B2_REGION=region
    B2_BUCKET_NAME=your-bucket-name
    PREFIX=optional-prefix

2. **Run the program**:
    `go run main.go`

## Dependencies
- AWS SDK for Go v2: under Apche2.0 License, see NOTICE2.txt
- godotenv: under MIT License https://mit-license.org/
  

## License
This project is licensed under the Apache2.0 License. See the LICENSE file for details.
Code base on https://github.com/awsdocs/aws-doc-sdk-examples, under Apache2.0 License, read NOTICE.
