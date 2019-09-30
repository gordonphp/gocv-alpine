# GoCV-compatible OpenCV 4.1.0 Alpine 3.7 Docker images

## What's in build-stage image?

 - Alpine 3.10
 - FFMPEG 4.2
 - Golang 1.13
 - OpenCV 4.1.1
 - OpenCV 4.1.1 contrib packages required by GoCV

## What's in runtime image?

 - Alpine 3.10
 - Whatever you need there

## Purpose

This is a build image for the multi-stage image provisioning as well as runtime image to work with gocv-based binaries.

## Example

Sample Docker file you can find [here](example/Dockerfile).

## Build the runtime image

```bash
pushd runtime && docker build -t yveshield/gocv-alpine:4.1.1-runtime .; popd
```

## Build the build-stage image

```bash
pushd build-stage && docker build -t yveshield/gocv-alpine:4.1.1-buildstage .; popd
```

## Test sample:

```bash
pushd example && docker build -t yveshield/gocv-alpine:test .; popd
```
```bash
docker run --rm -ti yveshield/gocv-alpine:test
```

the output should be the following:
```bash
gocv version: 0.18.0
opencv lib version: 4.1.1
```
