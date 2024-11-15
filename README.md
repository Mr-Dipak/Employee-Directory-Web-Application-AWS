# Employee Directory web Application ( AWS PROJECT )

This is a server for an employee directory application built with Node.js, Express, and AWS services.

## Table of Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [License](#license)

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/Mr-Dipak/Employee-Directory-Web-Application-AWS
    cd employee-directory-application
    ```

2. Install the dependencies:
    ```sh
    npm install
    ```

## Configuration

1. Create a `.env` file in the root directory and add the following environment variables:
    ```env
    NODE_ENV=development
    PORT=8081
    AWS_PROFILE=default
    PHOTOS_BUCKET=<your-s3-bucket-name>
    DEFAULT_AWS_REGION=<your-aws-region>
    SHOW_WARNINGS=1
    SHOW_ADMIN_TOOLS=0
    ```

2. Update the `constants.js` file in the `api/common` directory if needed:
    ```js
    exports.NODE_ENV = process.env.NODE_ENV || 'production';
    exports.PORT = process.env.PORT || 80;
    exports.AWS_PROFILE = process.env.AWS_PROFILE || 'default';
    exports.PHOTOS_BUCKET = process.env.PHOTOS_BUCKET || '';
    exports.DEFAULT_AWS_REGION = process.env.DEFAULT_AWS_REGION || '';
    exports.SHOW_WARNINGS = process.env.SHOW_WARNINGS || 1;
    exports.SHOW_ADMIN_TOOLS = process.env.SHOW_ADMIN_TOOLS || 0;
    exports.TABLE_NAME = 'Employees';
    ```

## Usage

1. Start the server:
    ```sh
    npm run start
    ```

2. For development mode:
    ```sh
    npm run start:dev
    ```

## API Endpoints

### Employees

- `GET /api/employees` - Get all employees
- `GET /api/employees/images` - Get all employee images
- `POST /api/employees/create` - Create a new DynamoDB table for employees
- `POST /api/employees/employee-photo` - Get an employee photo
- `POST /api/employees/get-upload-url` - Get a signed URL for uploading an employee photo
- `PUT /api/employees/add` - Add a new employee
- `PUT /api/employees/update` - Update an existing employee
- `DELETE /api/employees/delete/:id` - Delete an employee by ID

### Settings

- `GET /api/settings` - Get application settings
- `GET /api/settings/info` - Get AWS instance information
- `POST /api/settings/stress` - Stress test the server
- `POST /api/settings/cpu` - Get CPU usage
- `POST /api/settings/set-bucket` - Set the S3 bucket name

## License

This project is licensed under the MIT License.
