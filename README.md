# host-root usage

**Important!**: **To avoid package version problems, in the Dockerfile file, it is necessary to replace the ubuntu version (or whatever) with the host version.**

    docker build -t host-root

Docker does not allow mount /, so:

    docker run --net = host -it --rm -v "/: / host-root" host-root

To execute all the commands within the mount point:

    chroot / host-root / bash

To execute only one command:

    chroot / host-root / dpkg -i /home/john.doe/code_1.28.2-1539735992_amd64.deb
