# Build Instructions

The base tag this release is branched from is https://github.com/dexidp/dex/tree/v2.37.0

### Build and Push Image to a Container Registry

In order to tag and push the docker image, define the following environment variables:

```
export DOCKER_IMAGE_NAME=<docker repository/docker namespace>
export DOCKER_TAG=<image tag>
export VZ_BASE_IMAGE=<base image>
```

Build and push the image to container registry:
```
 make docker-build
 docker image push ${DOCKER_IMAGE_NAME}/:${DOCKER_TAG}
```

Please note the following changes made to build Dex from source:
- The Dex docker image is built using Dockerfile_verrazzano
- The calls to cross-compilation helpers - xx, is removed in Dockerfile_verrazzano
-
