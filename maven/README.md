<!--

********************************************************************************

WARNING:

    DO NOT EDIT "maven/README.md"

    IT IS AUTO-GENERATED

    (from the other files in "maven/" combined with a set of templates)

********************************************************************************

-->

# Supported tags and respective `Dockerfile` links


-	[`3.5.2-jdk-7-slim` (*jdk-7-slim/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/93d297ed2fc952af8c3638eae78c3d5e7526033f/jdk-7-slim/Dockerfile)
-	[`3.5.2-jdk-7` (*jdk-7/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/93d297ed2fc952af8c3638eae78c3d5e7526033f/jdk-7/Dockerfile)
-	[`3.5.2-jdk-8-slim`, `3.5.2-slim` (*jdk-8-slim/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/93d297ed2fc952af8c3638eae78c3d5e7526033f/jdk-8-slim/Dockerfile)
-	[`3.5.2-jdk-8`, `3.5.2` (*jdk-8/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/93d297ed2fc952af8c3638eae78c3d5e7526033f/jdk-8/Dockerfile)
-	[`3.5.2-jdk-9-slim` (*jdk-9-slim/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/93d297ed2fc952af8c3638eae78c3d5e7526033f/jdk-9-slim/Dockerfile)
-	[`3.5.2-jdk-9` (*jdk-9/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/93d297ed2fc952af8c3638eae78c3d5e7526033f/jdk-9/Dockerfile)
-	[`3.5-jdk-7-slim`, `3-jdk-7-slim` (*jdk-7-slim/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/d2e41bb4b98f827e7929eb01578538854a61726b/jdk-7-slim/Dockerfile)
-	[`3.5-jdk-7`, `3-jdk-7` (*jdk-7/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/d2e41bb4b98f827e7929eb01578538854a61726b/jdk-7/Dockerfile)
-	[`3.5-jdk-8-slim`, `3.5-slim`, `3-jdk-8-slim`, `slim` (*jdk-8-slim/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/d2e41bb4b98f827e7929eb01578538854a61726b/jdk-8-slim/Dockerfile)
-	[`3.5-jdk-8`, `3.5`, `3-jdk-8`, `3`, `latest` (*jdk-8/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/d2e41bb4b98f827e7929eb01578538854a61726b/jdk-8/Dockerfile)
-	[`3.5-jdk-9-slim`, `3-jdk-9-slim` (*jdk-9-slim/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/d2e41bb4b98f827e7929eb01578538854a61726b/jdk-9-slim/Dockerfile)
-	[`3.5-jdk-9`, `3-jdk-9` (*jdk-9/Dockerfile*)](https://github.com/carlossg/docker-maven/blob/d2e41bb4b98f827e7929eb01578538854a61726b/jdk-9/Dockerfile)

[![Build Status](https://doi-janky.infosiftr.net/job/multiarch/job/arm32v7/job/maven/badge/icon) (`arm32v7/maven` build job)](https://doi-janky.infosiftr.net/job/multiarch/job/arm32v7/job/maven/)

# Quick reference

-	**Where to get help**:  
	[the Docker Community Forums](https://forums.docker.com/), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack/), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

-	**Where to file issues**:  
	[https://github.com/carlossg/docker-maven/issues](https://github.com/carlossg/docker-maven/issues)

-	**Maintained by**:  
	[the Maven Project](https://github.com/carlossg/docker-maven)

-	**Supported architectures**: ([more info](https://github.com/docker-library/official-images#architectures-other-than-amd64))  
	[`amd64`](https://hub.docker.com/r/amd64/maven/), [`arm32v5`](https://hub.docker.com/r/arm32v5/maven/), [`arm32v6`](https://hub.docker.com/r/arm32v6/maven/), [`arm32v7`](https://hub.docker.com/r/arm32v7/maven/), [`arm64v8`](https://hub.docker.com/r/arm64v8/maven/), [`i386`](https://hub.docker.com/r/i386/maven/), [`ppc64le`](https://hub.docker.com/r/ppc64le/maven/), [`s390x`](https://hub.docker.com/r/s390x/maven/)

-	**Published image artifact details**:  
	[repo-info repo's `repos/maven/` directory](https://github.com/docker-library/repo-info/blob/master/repos/maven) ([history](https://github.com/docker-library/repo-info/commits/master/repos/maven))  
	(image metadata, transfer size, etc)

-	**Image updates**:  
	[official-images PRs with label `library/maven`](https://github.com/docker-library/official-images/pulls?q=label%3Alibrary%2Fmaven)  
	[official-images repo's `library/maven` file](https://github.com/docker-library/official-images/blob/master/library/maven) ([history](https://github.com/docker-library/official-images/commits/master/library/maven))

-	**Source of this description**:  
	[docs repo's `maven/` directory](https://github.com/docker-library/docs/tree/master/maven) ([history](https://github.com/docker-library/docs/commits/master/maven))

-	**Supported Docker versions**:  
	[the latest release](https://github.com/docker/docker-ce/releases/latest) (down to 1.6 on a best-effort basis)

# What is Maven?

[Apache Maven](http://maven.apache.org) is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build, reporting and documentation from a central piece of information.

![logo](https://raw.githubusercontent.com/docker-library/docs/e2782b8942c1af41419536078c8d0176665a005d/maven/logo.png)

# How to use this image

## Create a Dockerfile in your Maven project

```dockerfile
FROM arm32v7/maven:3.2-jdk-7-onbuild
CMD ["do-something-with-built-packages"]
```

Put this file in the root of your project, next to the pom.xml.

This image includes multiple ONBUILD triggers which should be all you need to bootstrap. The build will `COPY . /usr/src/app` and `RUN mvn install`.

You can then build and run the image:

```console
$ docker build -t my-maven .
$ docker run -it --name my-maven-script my-maven
```

## Run a single Maven command

For many simple projects, you may find it inconvenient to write a complete `Dockerfile`. In such cases, you can run a Maven project by using the Maven Docker image directly, passing a Maven command to `docker run`:

```console
$ docker run -it --rm --name my-maven-project -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven arm32v7/maven:3.2-jdk-7 mvn clean install
```

# Image Variants

The `arm32v7/maven` images come in many flavors, each designed for a specific use case.

## `arm32v7/maven:<version>`

This is the defacto image. If you are unsure about what your needs are, you probably want to use this one. It is designed to be used both as a throw away container (mount your source code and start the container to start your app), as well as the base to build other images off of.

## `arm32v7/maven:slim`

This image does not contain the common packages contained in the default tag and only contains the minimal packages needed to run `arm32v7/maven`. Unless you are working in an environment where *only* the `arm32v7/maven` image will be deployed and you have space constraints, we highly recommend using the default image of this repository.

# License

View [license information](https://www.apache.org/licenses/) for the software contained in this image.

As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).

Some additional license information which was able to be auto-detected might be found in [the `repo-info` repository's `maven/` directory](https://github.com/docker-library/repo-info/tree/master/repos/maven).

As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.
