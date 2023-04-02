# Coti Fullnode Image Builder

This repository periodically checks the releases of the official [coti-node](https://github.com/coti-io/coti-node/releases) repository, and when a new release is found, a Docker image of the release is built and pushed to [Dockerhub](https://hub.docker.com/r/atomnode/coti-node/tags). This process is handled entirely using GitHub actions. The advantage of doing the builds this way, is that it allows not just the code behind the builds to be open source, but also the executions of the builds themselves are transparent and public too. 

These images are produced by a Coti community member, with the goal of producing high quality and reliable Docker images for the Coti community to use as they wish.

Please dig in to the code. This repository has deliberately been kept small, so that the images stay as close as possible to how the Coti team intend for their software to be used. 

If you have ideas or input for the Coti node images, please feel free to let me know or make a pull request.

# 🔨 The Build Process

The most important file in the build process, is the GitHub actions workflow: [.github/workflows/update-image.yml](https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml). 

Most of the workflow file is standard to a GitHub action that builds a container image and pushes it to a container registry. The only modification to the main coti-node repository, is that a script called [create-properties](https://github.com/tj-wells/coti-node-images/blob/master/create-properties) is included, which allows node operators to generate `fullnode.properties` file from environment variables and downloads the appropriate clusterstamp file.

# Previous Builds

The fact that there are many workflow runs makes it challenging to locate the workflow runs that actually created new Docker images. The table below is used to log the workflow runs that created new Docker images of the Coti software.

| Coti Node Version |                                          Workflow Run                                          |                                                                            Dockerhub Image                                                                             |
| :---------------: | :--------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|       [3.1.3](https://github.com/coti-io/coti-node/releases/tag/3.1.3)       | [4400299976](https://github.com/tomjwells/coti-node-images/actions/runs/4400299976) | [3.1.3](https://hub.docker.com/layers/atomnode/coti-node/3.1.3/images/sha256-f5f7e78d8e03fbda62f6840eda2efd2610db9029d0f60b3696bc5cf8b3d44a3f?context=repo) |

# How do I use these images?

[This repository](https://github.com/tomjwells/coti-node) contains a `docker-compose.yml` file and a guide for running a Coti node with Docker.

# Stay Coti

Stay Coti. ️‍🔥

<p align="center"><a href="https://atomnode.tomoswells.com" target="_blank"><img src="https://media.discordapp.net/attachments/465686348234358804/1088843067425050784/atoms-3-01.png?width=852&height=850" style="width: 330px"></a></p>
