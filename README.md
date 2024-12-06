# OpenSourceSmith

OpenSourceSmith is a platform designed to empower developers by providing curated open-source templates for frontend, backend, and full-stack applications. Our goal is to streamline the development process, allowing you to start your next project in minutes with ready-to-use resources. Whether you're a beginner or an experienced developer, our tools are designed to save you time and effort, enabling you to focus on building great software.

## Links

- **Platform**: [OpenSourceSmith](https://opensourcesmith.vercel.app/)
- **Documentation**: [OpenSourceSmith Docs](https://amomynus.mintlify.app/introduction)
- **CLI Tool**: [open-source-smith](https://www.npmjs.com/package/open-source-smith)

## Purpose

The purpose of OpenSourceSmith is to connect developers with the best open-source resources, tailored to kickstart their journey. Our platform offers a wide range of templates, seamless GitHub integration, and a powerful CLI tool to generate project setup steps from README, Dockerfile to GitHub Actions.

## Tech Stack

OpenSourceSmith is built using the following technologies:

- **Next.js**: For server-side rendering and static site generation.
- **Vercel**: For seamless deployment and hosting.
- **Postgres**: For database management.
- **CopilotKit**: The simplest way to integrate production-ready Copilots into any product.
- **ShadCN**: For creating beautiful and consistent UI designs.
- **Tailwind CSS**: For building responsive and modern designs.
- **Google Gemini**: For advanced AI capabilities with CopilotKit.
- **NextAuth**: For secure and flexible authentication solutions.
- **Mintlify**: For documentation platform.
- **Prisma**: For next-generation ORM for Node.js and TypeScript.

## Usage

To get started with OpenSourceSmith, follow these steps:

1. **Explore Templates**: Browse our collection of ready-to-use templates for various types of applications.
2. **GitHub Integration**: Upload templates directly from your GitHub repository and share them with the community.
3. **CLI Tool**: Use our CLI tool, open-source-smith, to streamline your development process and generate project setup steps.

## Features

- **Ready-to-Use Templates**: Start your next project in minutes with our curated collection of templates.
- **GitHub Integration**: Seamlessly integrate your existing projects and share them with the community.
- **Open-Source CLI Tool**: Streamline your development process with our CLI tool.
- **Beginner-Friendly**: Tools designed to save you time and effort, regardless of your experience level.
- **Comprehensive Documentation**: Detailed guides to help you get started quickly.

## Tools and Libraries Used

- **Vercel**: For deployment and hosting.
- **Neon Postgres**: For database management.
- **Next.js**: For server-side rendering and static site generation.
- **CopilotKit**: For integrating LLM capabilities.
- **ShadCN**: For UI design.
- **Tailwind CSS**: For responsive design.
- **Google Gemini**: For AI capabilities.
- **NextAuth**: For authentication.
- **Mintlify**: For static site generation.
- **devcontainer**: For development environment management.


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
4. **Configure Environment Variables**:  
  To configure the environment variables, you need to obtain the following:

  - `DATABASE_URL`: This should be the Postgres database connection URL.
  - `GEMINI_API_KEY`: This is the API key for accessing the Gemini API. You can get it from [here](https://ai.google.dev/gemini-api/docs).
  - `NEXTAUTH_URL`: This is the URL of your NextAuth.js application. It should be the base URL of your deployed application. For development, it should be `http://localhost:3000`.
  - `NEXTAUTH_SECRET`: This is a secret key used by NextAuth.js to encrypt session data. To generate a secure secret key, you can use the following command:
    ```bash
    openssl rand -base64 32
    ```
  - `GITHUB_ID`: This is the Client ID for GitHub OAuth. You can get this by registering your application on GitHub.
  - `GITHUB_SECRET`: This is the Client Secret for GitHub OAuth. You can get this by registering your application on GitHub.

  **Make sure to keep these values secure and do not expose them in your source code.**

5. **Start the Application**:
   ```bash
   npm run dev
   ```



## What is Daytona?

Daytona is an open-source Development Environment Manager (DEM) licensed under the Apache License 2.0. Daytona allows you to manage and deploy Workspaces — reproducible development environments based on standard OCI containers, with built-in support for the Dev Container standard. Daytona’s architecture provides the future possibility to base Workspaces on other configuration standards, such as Dockerfiles, Docker Compose, Nix, and Devfile.

By leveraging configuration in a project’s remote Git repository, Daytona builds a Workspace and provisions a workspace to a platform of your choice. Once provisioned, you can develop and test the project using an IDE supported by Daytona, such as Visual Studio Code.

Daytona’s functionality is exposed through a command-line tool that runs on Linux, macOS, and Windows systems, on both x86-64 and AArch64 architectures.

For more information about Daytona, visit the [Daytona documentation site](https://www.daytona.io/docs/).


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