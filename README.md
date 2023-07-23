# ROS Dev Container Workflow Template

This repository provides a template for creating a holistic workspace for ROS software stacks. This workflow takes advantage of Dev Containers, Docker, and Docker Compose in order to make the process of developing and deploying ROS projects easier.

## Setup

1. Install Docker. If on Windows, install the latest WSL 2 version.
2. Install a Dev Containers tool - this could be a CLI or the Dev Container extension for Visual Studio Code.
3. Create a project in a manner similar to that in this repository. This repository is intended as a demonstration, with ideally the correct Dockerfiles to support easy rendering on your local machine.

## Example of a Docker / Dev Container Project

```
├── .devcontainer
│   ├── devcontainer.json
│   ├── docker-compose.yml
│   ├── docker-compose.deploy.yml # could be for development or deployment
├── ros_ws
│   ├── Dockerfile
│   ├── pkg1
│   │   ├── src
│   ├── pkg2
│   │   ├── .devcontainer
│   │   ├── src
├── other_ws
│   ├── Dockerfile
│   ├── ros.repos # install with vcstool
└── .gitignore
```

### .devcontainer

The .devcontainer directory consists of:
- `devcontainer.json` - a file describing how to set up your Dev Containers environment
- `docker-compose.yml` - the base docker-compose yaml file
- `docker-compose.{extension}.yml` - a docker-compose yaml file that can extend and override settings in the base file, potentially for differing development and deployment settings

### ros_ws

The `ros_ws` directory could be a catkin or colcon workspace. It can contain:
- `Dockerfile` - a file describing the environment in which all packages in this workspace will be built
- ROS packages (or directories containing packages) - the ROS packages that will be built in the Docker environment described by Dockerfile
    - ROS packages themselves could container .devcontainers for development in isolation
- `ros.repos` - a file for use with `vcstool` for importing packages from other sources
