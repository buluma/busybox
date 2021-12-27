# Busybox base images

[![busybox latest](https://github.com/buluma/busybox/actions/workflows/build-1.34.yml/badge.svg?branch=main)](https://github.com/buluma/busybox/actions/workflows/build-1.34.yml) [![busybox 1.34-glibc, glibc](https://github.com/buluma/busybox/actions/workflows/1.34.1-glibc.yml/badge.svg?branch=main)](https://github.com/buluma/busybox/actions/workflows/1.34.1-glibc.yml) [![busybox 1.34-musl, musl](https://github.com/buluma/busybox/actions/workflows/1.34.1-musl.yml/badge.svg?branch=main)](https://github.com/buluma/busybox/actions/workflows/1.34.1-musl.yml) [![busybox 1.34-uclibc, uclibc](https://github.com/buluma/busybox/actions/workflows/1.34.1-uclibc.yml/badge.svg?branch=main)](https://github.com/buluma/busybox/actions/workflows/1.34.1-uclibc.yml)

## Quick reference

    Maintained by: the Docker Community

    Where to get help: the Docker Community Forums, the Docker Community Slack, or Stack Overflow

## Supported tags and respective Dockerfile links

    1.34.1-uclibc, 1.34-uclibc, 1-uclibc, stable-uclibc, uclibc
    1.34.1-glibc, 1.34-glibc, 1-glibc, stable-glibc, glibc
    1.34.1-musl, 1.34-musl, 1-musl, stable-musl, musl
    1.34.1, 1.34, 1, stable, latest

## Quick reference (cont.)

    Where to file issues: https://github.com/docker-library/busybox/issues

    Supported architectures: (more info) amd64, arm32v5, arm32v6, arm32v7, arm64v8, i386, mips64le, ppc64le, riscv64, s390x

    Published image artifact details: repo-info repo's repos/busybox/ directory (history) (image metadata, transfer size, etc)

    Image updates: official-images repo's library/busybox label
    official-images repo's library/busybox file (history)

    Source of this description: docs repo's busybox/ directory (history)

## What is BusyBox? The Swiss Army Knife of Embedded Linux

Coming in somewhere between 1 and 5 Mb in on-disk size (depending on the variant), [BusyBox](http://www.busybox.net/) is a very good ingredient to craft space-efficient distributions.

BusyBox combines tiny versions of many common UNIX utilities into a single small executable. It provides replacements for most of the utilities you usually find in GNU fileutils, shellutils, etc. The utilities in BusyBox generally have fewer options than their full-featured GNU cousins; however, the options that are included provide the expected functionality and behave very much like their GNU counterparts. BusyBox provides a fairly complete environment for any small or embedded system.

    wikipedia.org/wiki/BusyBox


## How to use this image
Run BusyBox shell

    $ docker run -it --rm busybox

This will drop you into an sh shell to allow you to do what you want inside a BusyBox system.
Create a Dockerfile for a binary

    FROM busybox
    COPY ./my-static-binary /my-static-binary
    CMD ["/my-static-binary"]

This Dockerfile will allow you to create a minimal image for your statically compiled binary. You will have to compile the binary in some other place like another container. For a simpler alternative that's similarly tiny but easier to extend, [see alpine](https://hub.docker.com/_/alpine/).

## Image Variants

The busybox images contain BusyBox built against various "libc" variants (for a comparison of "libc" variants, [Eta Labs has a very nice chart](http://www.etalabs.net/compare_libcs.html) which lists many similarities and differences).

For more information about the specific particulars of the build process for each variant, see Dockerfile.builder in the same directory as each variant's Dockerfile (see links above).

`busybox:uclibc`

[uClibc](https://uclibc.org/) via [Buildroot](https://buildroot.org/) (statically compiled)

`busybox:glibc`

[glibc from Debian](https://packages.debian.org/search?searchon=names&exact=1&suite=all&section=all&keywords=libc6) (which is then included in the image)

`busybox:musl`

 [musl from Alpine](https://pkgs.alpinelinux.org/packages?name=musl) (statically compiled)
