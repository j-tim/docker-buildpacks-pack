# Buildpacks.io Pack

CLI for building apps using [Cloud Native Buildpacks](https://buildpacks.io/) using Docker!

Docker image based on Cloud Native Buildpacks ([buildpacks.io](https://buildpacks.io/))

* [Pack releases](https://github.com/buildpack/pack/releases)

## Latest version

* Docker: 18.09.1
* Buildpacks.io Pack: v0.0.9

## Supported tags and respective Dockerfile links

* `v0.0.9`, `[latest](https://github.com/j-tim/docker-buildpacks-pack/blob/master/v0.0.9/Dockerfile)`

## Example how to build a project using Gitlab CI (.gitlab-ci.yml)

```yml
pack-job:
  image: jtim/docker-buildpacks-pack:v0.0.9
  stage: dockerize
  services:
    - docker:dind
  script:
    - echo $CI_JOB_TOKEN | docker login -u gitlab-ci-token --password-stdin registry.gitlab.com
    - pack build $CI_REGISTRY_IMAGE
    - docker push $CI_REGISTRY_IMAGE
```

## Automated build for Dockerhub

See dockerhub: [https://hub.docker.com/r/jtim/docker-buildpacks-pack](https://hub.docker.com/r/jtim/docker-buildpacks-pack)