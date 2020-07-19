# containers-from-scratch
Writing a container in a few lines of Go code, as seen at DockerCon 2017

Prerequisites
-------------
* Linux Operating system
* Go
* Root access

Setup
-----
* Download a linux fs(filesystem) say ubuntu from http://cloud-images.ubuntu.com/minimal/releases/focal/release/ubuntu-20.04-minimal-cloudimg-amd64-root.tar.xz
* Extract above tar to a folder say '/rootfs' (can be any folder)

Run
---
* Edit main.go line-no#63: must(syscall.Chroot("/home/mike/src/centos/")) => must(syscall.Chroot("/rootfs"))
* Login as root and run as: go run main.go run [command]
  Example: go run main.go run echo Hello
           go run main.go run /bin/bash
