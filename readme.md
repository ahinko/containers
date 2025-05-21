# Container images

Images that exists in this repo does so for one of two reasons:
* Dockerhub has implemented more restrictive rate limiting. This repos is my way of trying to handle that limitation. The idea is simple. Let Renovate update the needed files and use Github workflows to build Docker images. The Dockerfiles in this repo are really simple, just a simple mirror of the versions on Dockerhub.
* I can't find or I want to maintain my own image for a specific app. Example: Postgres container with extentions that I need.

**Please note that I will remove apps from this repo/registry when official alternatives exists (that are not Dockerhub).**
