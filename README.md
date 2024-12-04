# OpenSourceSmith

### Open Using Daytona

1. **Install Daytona**: Follow the [Daytona installation guide](https://www.daytona.io/docs/installation/installation/).
2. **Create the Workspace**:
   ```bash
   daytona create https://github.com/md-abid-hussain/open-source-smith-daytona.git
   ```
3. **Configure Environment Variables**:  
   Copy the `.env.example` file to `.env` and update the environment variables with your own values.

   ```bash
   cp .env.example .env
   ```

4. **Start the Application**:
   ```bash
   npm run dev
   ```

---

## ✨ Features

- **Next.js**: A React framework for building fast and user-friendly web applications.
- **Tailwind CSS**: A utility-first CSS framework for rapid UI development.
- **Prisma**: A next-generation ORM for Node.js and TypeScript.
- **NextAuth**: Authentication for Next.js applications.
- **Dev Containers**: Standardized development environments using Docker.

---

## What is Daytona?

Daytona is an open-source Development Environment Manager (DEM) licensed under the Apache License 2.0. Daytona allows you to manage and deploy Workspaces — reproducible development environments based on standard OCI containers, with built-in support for the Dev Container standard. Daytona’s architecture provides the future possibility to base Workspaces on other configuration standards, such as Dockerfiles, Docker Compose, Nix, and Devfile.

By leveraging configuration in a project’s remote Git repository, Daytona builds a Workspace and provisions a workspace to a platform of your choice. Once provisioned, you can develop and test the project using an IDE supported by Daytona, such as Visual Studio Code.

Daytona’s functionality is exposed through a command-line tool that runs on Linux, macOS, and Windows systems, on both x86-64 and AArch64 architectures.

---

## Devcontainer Configuration

The Daytona configuration for this project is located in the `.devcontainer` directory. The `devcontainer.json` file specifies the development environment settings, including the Docker image, forwarded ports, VS Code extensions, and post-create commands.

```json
{
  "name": "Next.js Development Environment",
  "image": "mcr.microsoft.com/devcontainers/typescript-node:1-20",
  "forwardPorts": [3000],
  "customizations": {
    "vscode": {
      "settings": {
        "typescript.tsdk": "/usr/local/lib/node_modules/typescript/lib",
        "eslint.nodePath": "/usr/local/lib/node_modules"
      },
      "extensions": [
        "GitHub.github-vscode-theme",
        "esbenp.prettier-vscode",
        "Prisma.prisma",
        "dbaeumer.vscode-eslint"
      ]
    }
  },
  "postCreateCommand": "npm install && npx prisma generate && npm run build"
}
```

Feel free to change it as per your need.
