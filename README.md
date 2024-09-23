# Laravel Demo

This repository demonstrates how to prepare a basic Laravel application for cloud deployment using Docker and FrankenPHP.

## Local Development Setup

### Prerequisites
- Docker
- Docker Compose

### Getting Started

1. Clone this repository
2. Copy `.env.example` to `.env` and set `APP_KEY`:

```text
APP_KEY=base64:your-app-key-here
```

3. Run the following command to start the development environment:

```bash
docker compose up --build
```

Access the application at http://0.0.0.0:8080

## Project Structure

- `Dockerfile`: Production Docker image configuration
- `compose.yml`: Docker Compose configuration for local development
- `.dockerignore`: Specifies files to be excluded from Docker builds


## Testing Production Image Locally

### Building the Production Image

To build the production Docker image locally:

```bash
docker build -t laravel-demo .
```

### Running the Production Image

To test the production image locally:

```bash
docker run -p 8080:8080 -e APP_KEY=base64:your-app-key-here laravel-demo
```

Replace your-app-key-here with your Laravel application key.

## Key Features

- Uses FrankenPHP runtime with Caddy web server
- Minimal configuration for a Laravel server

## Deployment Steps for Sevalla

1. Create a new app on Sevalla (deploy later)
2. Change the app's build settings to be based on Dockerfile
3. Set the required environment variable: `APP_KEY`
4. Deploy your application

## Customization
This setup provides a basic Laravel server. To add more features or customize the application:
- Modify the Laravel application code in the app directory
- Update the `Dockerfile` if you need to install additional dependencies
- Adjust the `compose.yml` file for any changes in local development setup

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
