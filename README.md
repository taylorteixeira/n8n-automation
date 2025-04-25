# n8n Automation Project

This repository contains a Docker-based setup for running [n8n](https://n8n.io/), a workflow automation tool that allows you to connect different services and automate tasks without coding.

## Overview

n8n is a free, fair-code licensed workflow automation tool that helps you connect various services and applications together in an easy-to-use visual interface. With n8n, you can create custom workflows, integrate diverse services, and automate repetitive tasks.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine
- [Docker Compose](https://docs.docker.com/compose/install/) installed on your machine
- Basic understanding of Docker and containerization

## Project Structure

```
n8n-automation/
├── binaryData/         # Storage for binary data used in workflows
├── git/                # Git configuration for version control
├── ssh/                # SSH configuration for secure connections
│   └── config          # SSH configuration file
├── database.sqlite     # SQLite database file for n8n
├── docker-compose.yml  # Docker Compose configuration
├── Makefile            # Makefile for common commands
├── n8nEventLog.log     # Log file for n8n events
└── README.md           # This documentation
```

## Getting Started

### Starting the Service

To start the n8n service:

```bash
docker-compose up -d
```

Or using the provided Makefile:

```bash
make up
```

### Accessing n8n

Once the service is running, you can access the n8n web interface at:

## Access URL:
http://localhost:5678/

### Stopping the Service

To stop the n8n service:

```bash
docker-compose down
```

Or using the provided Makefile:

```bash
make deploy
```

## Configuration

The `docker-compose.yml` file contains the configuration for the n8n service. You can modify this file to adjust settings like ports, environment variables, and volume mounts.

## Data Persistence

All n8n data is persisted in the following locations:
- Workflows and credentials: `database.sqlite`
- Binary data: `binaryData/` directory

## Common Issues & Troubleshooting

If you encounter any issues:

1. Check the logs with `docker-compose logs n8n`
2. Review the `n8nEventLog.log` file for detailed error information
3. Ensure all required ports are available (especially port 5678)

## Maintenance

### Updating n8n

To update to the latest version of n8n:

```bash
docker-compose pull
docker-compose down
docker-compose up -d
```

### Backup

It's recommended to regularly back up the `database.sqlite` file and the `binaryData` directory.

## Resources

- [n8n Documentation](https://docs.n8n.io/)
- [n8n Community Forum](https://community.n8n.io/)
- [Docker Documentation](https://docs.docker.com/)

## License

This project setup is provided under the [MIT License](https://opensource.org/licenses/MIT). n8n itself is licensed under the [fair-code license](https://docs.n8n.io/reference/license/).