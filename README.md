# Dockerfile Generator
A project to automatically generate Dockerfiles to build container images based on Alpine Linux and a selection of compilers and tools.

## Context
Creating a Docker container image means stacking layer upon layer of software configurations; this is efficient in terms of intermediate images reuse but it may end up creating lots and lots of layers, especially when the setup of a build environment is quite complicated.
This Dockerfile generator makes an assumption: each compiler and/or build tool can be configured by applying to a Golang template the information taken from a YAML file.
Under Gitlab-CI, builds happen inside containers, and the more lightweight the container image, the better the resource usage on the runners. Thus, I wanted to create a tool that would help me keep my builder containers up-to-date with little effort; since Dockerfiles are text files in the end and Golang support for templates, YAML and JSON is very powerful and easy, the choice was quite straightforward.
The tools allows to tailor the container image around one's needs by adding compilers and tools as necessary; for instance, it may be used to generate a Dockerfile for a container having the Oracle JDK 8, Apache Maven and maybe a C/C++ compiler for some native (JNI) classes.

## Thanks
Inspiration was drawn from the excellent work done by Anastas Dancha and made available on GitHub and DockerHub (see https://github.com/anapsix/docker-alpine-java for details); it is simply meant to add more languages and compilers to what he's already done.