# README for  `map_align` <img src="logo.svg" align="right" alt="" width="120" />

Github repository for the [podman](https://podman.io/) conatiner [`map_align`](https://hub.docker.com/repository/docker/khench/map_align).

## Documentation of the initial setup

Originally, the `map_align` container was build using [buildah](https://buildah.io/), from the accompanying `Containerfile`:

```sh
buildah bud -t map_align
```

To make the container publicly available, it is pushed to [dockerhub](https://hub.docker.com/r/khench/map_align) using [skopeo](https://github.com/containers/skopeo) and [podman](https://podman.io/):

```sh
skopeo login -u khench docker.io
podman push localhost/map_align docker.io/khench/map_align:v0.2
```

## Accessing the container

The bundled software can be accessed directly from [dockerhub](https://hub.docker.com/r/khench/map_align) with `podman` (or `docker`, or `singularity`):

```sh
podman run docker.io/khench/map_align:v0.2 which bwa
singularity run docker://khench/map_align:v0.2 which bwa
```