# Coti Node Image Builder

This repository uses GitHub Actions to periodically check for new coti-node <a href="https://github.com/coti-io/coti-node/releases" target="_blank">releases</a>, and if a new release is available, a container image of the release is automatically built and pushed to [Dockerhub](https://hub.docker.com/r/atomnode/coti-node/tags) in an open-source and publicly transparent way, so that the generated images can be trusted. These images are produced by the Coti community, for the Coti community to use as they wish.

Please dig in to the code. If you have ideas or input for the Coti node images, please feel free to let me know or make a pull request.

# What does this Repository do?

This repository uses <a href="https://docs.github.com/en/actions">GitHub Actions</a> to check for new releases of the <a href="https://github.com/coti-io/coti-node">official coti-node repository</a>, and if a new version is found, it builds a Docker image of the new release, and pushes it to Dockerhub.

Below is a description of the important components to this repository:

- [.github/workflows/update-image.yml](https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml) - The GitHub Action workflow file itself, that describes the build process
- [create-properties](https://github.com/tj-wells/coti-node-images/blob/master/create-properties) - A script that generates a  `fullnode.properties` file from the environment variables within the Docker container. It also downloads the appropriate clusterstamp file for MainNet or TestNet when necessary.
- [check-for-new-release](https://github.com/tomjwells/coti-node-images/blob/master/check-for-new-release) - A short python script that checks whether the latest Coti release version is equal to the most recent Dockerhub image tag.  
- [Dockerhub container registry](https://hub.docker.com/r/atomnode/coti-node) - Where the images produced by this repository are stored.
- [GitHub Actions workflow runs](https://github.com/tj-wells/coti-node-images/actions)

# 🐳 Overview of the Build Process

This section gives a high-level overview of the build process executed by <a href="https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml" target="_blank">this workflow file</a>.

Most of the workflow file is general to any GitHub action that builds a container image and pushes it to a container registry. The important step, in which slight modifications are made to the basic Coti node repository, is one called "Modify coti-node Repository", which performs the following operations before executing the build:

1. Clones the official Coti release.
2. Copy a script ([create-properties](https://github.com/tj-wells/coti-node-images/blob/master/create-properties)), which uses the container's environment variables to generate a new `fullnode.properties` file.

# Workflow runs that created previous images

Since there are many workflow runs in which no image is built, it can be difficult to find the workflow runs that actually created new Docker images. The table below is used to keep a log of the Docker images of each new version of the Coti software and the workflow runs that built them.

| Coti Node Version |                                          Workflow Run                                          |                                                                            Dockerhub Image                                                                             |
| :---------------: | :--------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|       [3.1.3](https://github.com/coti-io/coti-node/releases/tag/3.1.3)       | [4200498828](https://github.com/tomjwells/coti-node-images/actions/runs/4200498828) | [3.1.3](https://hub.docker.com/layers/atomnode/coti-node/3.1.3/images/sha256-0bef7395d3de26da3af5a04d37301f7d5e5d13a6f4e43d68a0c5a5ead727bb20?context=repo) |

# How Can I Use these Docker Images?

See [this repository](https://github.com/tomjwells/coti-node) for an example and accompanying guide that suggests a method for running a Coti node using Docker. This repository contains the exact `docker-compose` files I use to run my node.

# Stay Coti

Stay Coti. ️‍🔥

<p align="center"><a href="https://atomnode.tomoswells.com" target="_blank"><img src="https://cdn.discordapp.com/avatars/343604221331111946/65130831872c9daabdb0d803ce27e594.webp?size=240"></a></p>
