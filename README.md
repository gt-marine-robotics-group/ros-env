# ROS Dev Container Workflow Template

This repository provides a template for creating a holistic workspace for ROS software stacks. This workflow takes advantage of Dev Containers, Docker, and Docker Compose in order to make the process of developing and deploying ROS projects easier.

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
