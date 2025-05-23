# Postgres 17 + VectorChord
My custom Postgres Docker images with extensions that I need. Based on Cloudnative-PGs Postgres Docker images.

## A note about Semver
Cloudnative-PG requires the Docker image to be tagged with Postgres version, i.e. 17.1 and so on. So there is no way of updating the major version if I have to introduce breaking changes to this image.

## Added extensions:

### [VectorChord](https://github.com/tensorchord/VectorChord)

> [!IMPORTANT]
> Enable the extension to both existing and new databases by adding the following to your Cluster spec.
> Note that the extension is only enabled. You still need to create it on each database you want to use it on (see below).
> ```yaml
> apiVersion: postgresql.cnpg.io/v1
> kind: Cluster
> spec:
>   (...)
>   postgresql:
>     shared_preload_libraries:
>       - "vchord.so"
>   ```
