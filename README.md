# ROS Docker Env Template

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
