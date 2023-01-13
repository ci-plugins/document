# Build and host a CI image
bk-ci provides a default Ubuntu image, but it may not be suitable for all compilation scenarios. You can use this article to create a custom image based on the default image.

* Default image: [bkci/ci:latest](https://github.com/ci-plugins/base-images)
## Prepare materials
* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* A linux build machine
* A Dockerfile project that can successfully build an image on the machine
## Customize CI images
1. Log in to the builder, synchronize the Dockerfile project to the builder, and enter the Dockerfile project directory
Dockerfile Example:
```text
FROM bkci/ci:latest

RUN yum install -y mysql-devel
```

1. Run docker build
> Important Note:>
> * Since the container in the pipeline is started by CMD with /bin/sh, make sure that the /bin/sh command and curl command (to download the Agent) are present in the image.
> * Do not set ENTRYPOINT
> * Ensure 64-bit mirroring
> * User root. If common users need to switch to bash, pipeline tasks cannot be started
```text
docker build -t XXX.com/XXX/YYY:latest -f Dockerfile .
```

1. Run docker login
```text
docker login XXX.com
```

1. Execute docker push
```text
docker push XXX.com/XXX/YYY:latest
```

## Attention
* Plug-ins may be developed in one or more languages, including Java, Python, Golang, and Nodejs. The mirroring environment must support execution in multiple languages
* [Python plugin execution environment](javascript:void%280%29)
* [NodeJS plugin execution environment](javascript:void%280%29)
## Next you may need
* [release a container image](image-release.md)
