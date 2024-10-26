Here's a `README.md` that should fit your needs for a custom Frappe build with Docker Compose for both x86 and ARM64, including instructions for installing the HRMS and Payment modules.

```markdown
# Custom Frappe Build with Docker Compose

This repository contains a custom Frappe build configured to work on both `x86` and `arm64` architectures, with `HRMS` and `Payments` modules included. The setup uses Docker Compose for easy deployment and management.

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/iamtrazy/erpnext-arm64-docker
   ```

2. **Navigate into the project directory**

   ```bash
   cd erpnext-arm64-docker
   ```

3. **Start Docker Compose**

   To start up the containers, run:

   ```bash
   docker compose up -d
   ```

   This command builds and runs the necessary services in detached mode.

4. **Install HRMS and Payment Modules**

   In a separate terminal, navigate back to the same project folder:

   ```bash
   cd erpnext-arm64-docker
   ```

   Then, access the Frappe backend service and install the modules:

   ```bash
   docker compose exec -it backend /bin/bash
   bench --site frontend install-app hrms
   bench --site frontend install-app payments
   ```

   This will install both the `HRMS` and `Payments` modules on the `frontend` site.

### Notes

- Ensure that you have the necessary permissions to run Docker commands.
- The backend service uses `frontend` as the site name, which can be customized in your Frappe setup.

### Troubleshooting

- **Docker permissions**: If you encounter permission issues with Docker, try running the commands with `sudo`.
- **Module errors**: Ensure that the `HRMS` and `Payments` modules are included in the `apps` directory and are compatible with your Frappe build.

### Stopping the Application

To stop the running containers, use:

```bash
docker compose down
```

This stops and removes all containers defined in the `compose.yml` file.

```
