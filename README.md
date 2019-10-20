# rsync Docker image

## What is this?

**rsync** is a well-known utility, commonly found on unix systems, for efficently synchronizing files and directories, by checking timestamps, sizes and/or chechsums of files.
This works on local files and remote directories, e.g. via ssh, thus serving as a secure file transfer tool.

This simple alpine based image simply contains **rsync** and the **openssh client**.

## How to use this image

### Simple synchronization of local directories

~~~bash
docker run --rm -it -v /tmp/foo:/source:ro -v /tmp/bar:/destiation 2shell/rsync -rv /source/ /destiation/
~~~

### Filetransfer via SSH

~~~bash
docker run --rm -it -v $HOME/.ssh:/root/.ssh:ro -v /tmp/foo:/source:ro 2shell/rsync -rv /source/ user@host:/tmp/foo/
~~~

## Issues

We don't monitor comments on DockerHub. If you have any problems with or questions about this image, please contact us via GitHub issues.

