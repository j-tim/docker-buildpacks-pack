# Buildpacks.io Pack

CLI for building apps using [Cloud Native Buildpacks](https://buildpacks.io/) using Docker!

Docker image based on Cloud Native Buildpacks ([buildpacks.io](https://buildpacks.io/))

* [Pack releases](https://github.com/buildpack/pack/releases)

## Latest version

* Docker: 18.09.1
* Buildpacks.io Pack: v0.0.9

* `v0.0.9`, `latest`

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
