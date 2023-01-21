# Coti Node Image Builder

This repository supplements the repository, <a href="https://github.com/tj-wells/coti-node" target="_blank">Coti Node Docker Installation Method</a>, which proposes a simple method for installing and maintaining Coti nodes using Docker containers.

This repository executes the build process of the coti-node images in an open-source and publicly transparent way, so that the images it generates can be trusted. In addition, others can produce their own images by cloning this repository and making variations.

# What does this Repository do?

This repository makes use of a Github actions workflow, to check for new releases of the coti-node in the <a href="https://github.com/coti-io/coti-node">official coti-node repository</a> every morning, and if a new version is available, it executes a build of the new release.

- To view the workflow file that shows the steps of the build process, <a href="https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml"  target="_blank">click here</a>.
- To view the historical runs of the workflows themselves, <a href="https://github.com/tj-wells/coti-node-images/actions"  target="_blank">click here</a>.
- To view the images built and pushed by this repository, <a href="https://hub.docker.com/r/atomnode/coti-node"  target="_blank">click here</a>.

# Overview of the Build Process

This section provides a high-level overview of the build process executed by <a href="https://github.com/tj-wells/coti-node-images/blob/master/.github/workflows/update-image.yml"  target="_blank">this workflow file</a>.

The steps implemented in the workflow are as follows.

1. Download the new official Coti release.
2. Copy a script (<a href="https://github.com/tj-wells/coti-node-images/blob/master/update-env" target="_blank">update-env</a>), which uses the container's environment variables to generate a new `fullnode.properties` file.

# Stay Coti

Stay Coti. ️‍🔥

<p align="center"><a href="https://twitter.com/tomjwells" target="_blank"><img src="https://cdn.discordapp.com/avatars/343604221331111946/65130831872c9daabdb0d803ce27e594.webp?size=240"></a></p>
