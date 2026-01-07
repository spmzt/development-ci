# FreeBSD Development CI for Jenkins

There are two pipelines here.

## Tests

The `tests` directory is for building new images and automatically running its
tests using kyua.
It works as follows:

* Pulls FreeBSD source code from a Git repository (set your own).
* Creates a poudriere jail by building the source code or updating an existing
one.
* Creates a VM image using poudriere.
* Populates the image with the required `rc.conf` and `rc.local` to start
testing immediately after it boots.
* Starts the image using vm-bhyve.

You must pre-configure your vm-bhyve environment to allow it to simply move the
testing image and run it.

## Release

Read the `Jenkinsfile` under the `release` directory to understand how it works.

