---
Layout: post
title: No Shi* Container Security Cheat Sheet
description: Covering most Container Security topics in brief
date: 10-02-2025
categories: [Blog, Containers]
tags: [containers, blog, docker, security]
---

![Container Security](assets/img/post_assets/Container Security.png){: width="800" height="400"}
_Container Security_

Before getting started, few important points. Read the following points out loud. Inspired by this section of the [video](https://youtu.be/qxmhfY05oWY?t=28).

* Say Container or OCI Container, not Docker Container.
* It's a Container Image, not a Docker Image.
* It's a Container Image Registry, not Docker Registry.
* Not everything in Container world is build for and around Docker.
* Docker is not the only platform to manager Containers.

Topics:

> Some contents have been `shamelessly` copied from internet and complied here for ease of use

- [Base Images](#base-images)
  - [Benefits of choosing right base images?](#benefits-of-choosing-right-base-images)
  - [How to choose a good base images?](#how-to-choose-a-good-base-images)
- [Container runtime security options](#container-runtime-security-options)
  - [AppArmor](#apparmor)
  - [Seccomp](#seccomp)
  - [Gsec](#gsec)
  - [SELinux](#selinux)
- [Host OS where Containers run](#host-os-where-containers-run)
- [Container Image Hardening Rabbit Hole](#container-image-hardening-rabbit-hole)
- [Use Podman](#use-podman)

## Base Images

First question yourself
: > Does it really matter for you?

And the obvious answer should be
: > YES!!

### Benefits of choosing right base images?

- [x] Lower image size
- [x] Faster container start time
- [x] Lower network bandwidth usage resulting lower network costs
- [x] Lower storage costs
- [x] Lower attack surface
- [x] Follows the least privileged principle
- [x] Has lesser image layers to cache
- [x] And many more

### How to choose a good base images?

Depends on your use case. If you are running a simple binary of your application where everything is bundled into one single binary like a GO binary, [scratch](https://hub.docker.com/_/scratch) images would be great for that.

Use alpine base images when ever possible. Few examples:

* [Base Alpine](https://hub.docker.com/_/alpine)
* [For Python](https://hub.docker.com/_/python/tags?name=alpine)
* [For Nginx](https://hub.docker.com/_/nginx/tags?name=alpine)

If you are running some heavy workloads like a GUI application, or applications that would utilize GPU or some other sort of hardware, network, etc functionalities, make your best decision and weigh in pros and cons of each base image you come through.


## Container runtime security options

Container runtime security is the process of safeguarding containerized applications during their execution phase. With robust container runtime security practices, applications operate securely and remain free from threats while serving users. And by focusing on runtime protection, organizations can protect their applications from unforeseen vulnerabilities that might emerge during this stage, maintaining the integrity and confidentiality of their data.

### AppArmor
[Wiki](https://en.wikipedia.org/wiki/AppArmor)
### Seccomp
### Gsec
### SELinux

## Host OS where Containers run

## Container Image Hardening Rabbit Hole

## Use Podman
