# Coti Node Image Builder

This repository supplements the repository, <a href="https://github.com/tj-wells/coti-node" target="_blank">Coti Node Docker Installation Method</a>, which proposes a simple method for installing and maintaining Coti nodes using Docker containers.

This repository periodically checks for new coti-node <a href="https://github.com/coti-io/coti-node/releases" target="_blank">releases</a>, and if a new release is found, a container image of the release is built in an open-source and publicly transparent way, so that the images it generates can be trusted.

If you have ideas for how the images can be improved, please feel free to let me know or make a pull request.

# What does this Repository do?

This repository uses Github actions to check for new releases of the <a href="https://github.com/coti-io/coti-node">official coti-node repository</a>, and if a new version is found, it builds a Docker image of the new release.

- To view the workflow file that shows the steps of the build process, <a href="https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml"  target="_blank">click here</a>.
- To view recent runs of the workflows themselves, <a href="https://github.com/tj-wells/coti-node-images/actions"  target="_blank">click here</a>.
- The images produced by this repository can be found in <a href="https://hub.docker.com/r/atomnode/coti-node"  target="_blank">this Dockerhub container registry</a>.

# Overview of the Build Process

This section gives a high-level overview of the build process executed by <a href="https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml" target="_blank">this workflow file</a>.

Most of the workflow file is general to any github action that builds a container image and pushes it to a container registry. The important step to understand is the one called "Modify coti-node Repository", which performs the following operations before executing the build:

1. Clone the official Coti release.
2. Copy a script (<a href="https://github.com/tj-wells/coti-node-images/blob/master/update-env" target="_blank">update-env</a>), which uses the container's environment variables to generate a new `fullnode.properties` file.

# Stay Coti

Stay Coti. ️‍🔥

<p align="center"><a href="https://twitter.com/tomjwells" target="_blank"><img src="https://cdn.discordapp.com/avatars/343604221331111946/65130831872c9daabdb0d803ce27e594.webp?size=240"></a></p>
