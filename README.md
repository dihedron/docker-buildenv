# docker-buildenv
A project to automatically generate Docker images based on Alpine Linux for the most common languages.

Creating a Docker container image means layering atack upon stack of software configurations; this is efficient in terms of intermediate images reuse but it may end up creating lots and lots of layers, especially when the setup of a build environment is quite complex.
The tool makes an assumption: each compiler and/or build tool can be configured by actualising a Golang template with information taken from a YAML file.

## Thanks
Inspiration was drawn from the excellent work done by Anastas Dancha and made available on GitHub and DockerHub (see https://github.com/anapsix/docker-alpine-java for details); it is simply meant to add more languages and compilers to what he's already done.