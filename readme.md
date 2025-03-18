# Container images

Dockerhub will soon (when writing this) implement more restrictive rate limiting. This repos is my way of trying to handle that limitation. The idea is simple. Let Renovate update the needed files and use Github workflows to build Docker images. The Dockerfiles in this repo are really simple, just a simple mirror of the versions on Dockerhub.

Github Actions/Workflows and repo structure is heavily inspired by the [home-operations/containers](https://github.com/home-operations/containers) repo.

Please note that I will remove apps from this repo/registry when official alternatives exists (that are not Dockerhub).
