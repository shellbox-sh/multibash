---
title: ""
---

# `$ multi-bash`

> _Verify your shell scripts work across multiple versions of BASH!_

---

<script src="https://kit.fontawesome.com/319dabc23d.js" crossorigin="anonymous"></script>

## <i class="fad fa-download"></i> Install

Download the [latest version](https://github.com/shellbox-sh/multi-bash/archive/v1.0.1.tar.gz) by clicking one of the download links above or:

```sh
curl -o- https://multibash.shellbox.sh/install.sh | bash
```

## <i class="fad fa-terminal"></i> Run

```sh
./multi-bash 3.2.57 bash --version

BASH image not installed locally for version: 3.2.57

Pulling image from Docker Hub...
3.2.57: Pulling from library/bash
Digest: sha256:81d765725efc7ef7994a8ec7363441...
Status: Downloaded newer image for bash:3.2.57
docker.io/library/bash:3.2.57

GNU bash, version 3.2.57(1)-release (x86_64-pc-linux-musl)
Copyright (C) 2007 Free Software Foundation, Inc.
```

The Docker image will only download if it is not already downloaded:

```sh
./multi-bash 5.0,3.2.57 bash --version

5.0
GNU bash, version 5.0.18(1)-release (x86_64-pc-linux-musl)
Copyright (C) 2019 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu...

This is free software; you are free to change and r...
There is NO WARRANTY, to the extent permitted by law.

3.2.57
GNU bash, version 3.2.57(1)-release (x86_64-pc-linux-musl)
Copyright (C) 2007 Free Software Foundation, Inc.
```

Run `multi-bash` without any commands to start an interactive Bash shell:

```sh
./multi-bash 4.4

4.4
bash-4.4# echo "Hello, world"
Hello, world
bash-4.4#
```

## <i class="fab fa-docker"></i> Docker

`multi-bash` runs using [Docker](https://www.docker.com/) and the [official bash image](https://hub.docker.com/_/bash).

 - [https://hub.docker.com/\_/bash](https://hub.docker.com/_/bash)

You can find instructions for installing Docker at:

- [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)

You can find all of the versions of Bash supported by `multi-bash` at:

 - [https://hub.docker.com/\_/bash](https://hub.docker.com/_/bash)

> <i class="fas fa-lightbulb-on"></i> Tip: Test with `3.2.57` to help verify your script's Mac OS support <i class="fab fa-apple"></i>

## <i class="fad fa-books"></i> Documentation

```
./multi-bash --help

Usage: ./multi-bash [BASH version],[BASH version] [command (optional)] [arguments]

If command is provided, it will be run in a Docker container of the specified BASH version(s).
If command is not provided, it will start an interactive BASH session. Use 'exit' to exit.

# BASH Docker Images

  If the provided BASH versions are not locally installed as Docker container images,
  the container images will be automatically downloaded and installed.
  
  To view all locally installed BASH docker images, run:
  
    docker images | grep ^bash
  
  To remove a locally installed BASH Docker container image for a specific BASH version, run:
  
    docker image rm bash:4.4

# BASH Versions Available

  For a list of available BASH versions, see the bash Docker image on Docker Hub:
  https://hub.docker.com/_/bash

# Configuration

  When the Docker container is run the current directory is mounted inside the container as /app.
  When a command is run, it is executed from the mounted folder, so it is run from inside /app.
  
  Set MULTIBASH_DIR="path/to/folder" to mount a directory other than the current directory.
  Set MULTIBASH_MOUNT=/path to mount the directory as a specific location in the container.
  Set MULTIBASH_WORKDIR="path/to/folder" to run commands from this location *inside* the container.

Visit https://multibash.shellbox.sh for official project documentation.
```