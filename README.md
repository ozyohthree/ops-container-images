# Ops Container Images

Author: Brian Tomlinson <btomlins@redhat.com> | <darthlukan@gmail.com>


## Description

This repository contains various container image definitions, e.g. `Dockerfiles`, that I've come up with as
a necessity when working in particularly locked-down environments where one is allowed little more than to
check corporate email, let alone produce working software features. Assuming access to a secured registry of 
some kind is available, notably, the [Red Hat Registry](https://registry.redhat.io), you should be able to
use at least some of these in order to have a modicum of productivity.

Most images use `registry.access.redhat.com/ubi8:latest` so there should be no issues with needing a login
or Red Hat Subscription in order to install and consume software. This was decided for two reasons:

1. I'm a Red Hatter and 100% believe our tools are awesome.
2. The Red Hat Registry is a secured registry and customers/enterprises typically allow it as a rule, but may not
   allow other public registries like [quay.io](https://quay.io) or [Docker Hub](https://hub.docker.com).


## Use

In general one should be able to pull, or in extreme cases, copy and paste, the `Dockerfiles` in this repo
to their local locked-down "development" machine, build the image locally, and then execute it. Even some of the
most locked-down enterprises allow access to a local `docker` or `podman` client. In those cases, the following
should suffice:

```
$ git pull https://github.com/darthlukan/ops-container-images.git
$ cd ops-container-images/${IMAGE_DIR}
$ podman build -f Dockerfile -t ${IMAGE_NAME}:${TAG}

// ${ARGS} or ${FLAGS} or both as appropriate...
$ podman run -it ${IMAGE_NAME}:${TAG} --${ARGS}||-{$FLAGS}
```


## License

MIT, see LICENSE file.
