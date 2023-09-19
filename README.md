# Coti Fullnode Image Builder

<p align="center">
	<a href="[https://github.com/tomjwells/coti-node](https://hub.docker.com/r/atomnode/coti-node/tags)"><img alt="Docker image size" src="https://img.shields.io/docker/image-size/atomnode/coti-node"></a>
</p>

This repository periodically checks for new versions of the official [coti-node](https://github.com/coti-io/coti-node/releases) repository, and when a new release is found, a Docker image of the release is built and pushed to [Dockerhub](https://hub.docker.com/r/atomnode/coti-node/tags). This process is handled using GitHub actions, which allows the builds themselves to be public as well as the code.

Please feel free to dig in to the code. This repository has deliberately been kept small, so that the images are as close as possible to how the Coti intend for their software to be used. 

If you have any input, please feel free to let me know or make a pull request.

# 🔨 The Build Process

The instructions for building the Docker image using Github actions are in the file [.github/workflows/update-image.yml](https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml). 

Most of the workflow file is common to GitHub actions that build a container image and upload it to a container registry. The only non-stadard step performed, is that a script called [create-properties](https://github.com/tj-wells/coti-node-images/blob/master/create-properties) is included. `create-properties` is a script that generates a `fullnode.properties` file using environment variables passed to the container, and downloads the appropriate clusterstamp file.

# Previous Builds

The table below logs the workflow runs that created new Docker images of the Coti software.

| Coti Node Version |                                          Workflow Run                                          |                                                                            Dockerhub Image                                                                             |
| :---------------: | :--------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|       [3.1.3](https://github.com/coti-io/coti-node/releases/tag/3.1.3)       | [4400299976](https://github.com/tomjwells/coti-node-images/actions/runs/4400299976) | [3.1.3](https://hub.docker.com/layers/atomnode/coti-node/3.1.3/images/sha256-f5f7e78d8e03fbda62f6840eda2efd2610db9029d0f60b3696bc5cf8b3d44a3f?context=repo) |

# How do I use these images?

[This repository](https://github.com/tomjwells/coti-node), contains `docker-compose` configuration files and a short guide for running a Coti node with Docker.

# Stay Coti

<p align="center"><a href="https://atomnode.tomoswells.com" target="_blank"><img src="https://pay.coti.io/nodes/atomnode.png" style="width: 200px"></a></p>
