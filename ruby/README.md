<!--

********************************************************************************

WARNING:

    DO NOT EDIT "ruby/README.md"

    IT IS AUTO-GENERATED

    (from the other files in "ruby/" combined with a set of templates)

********************************************************************************

-->

# Supported tags and respective `Dockerfile` links

**No supported tags found!**

It is very likely that `ruby` does not support the currently selected architecture (`windows-amd64`).

# Quick reference

-	**Where to get help**:  
	[the Docker Community Forums](https://forums.docker.com/), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack/), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

-	**Where to file issues**:  
	[https://github.com/docker-library/ruby/issues](https://github.com/docker-library/ruby/issues)

-	**Maintained by**:  
	[the Docker Community](https://github.com/docker-library/ruby)

-	**Supported architectures**: ([more info](https://github.com/docker-library/official-images#architectures-other-than-amd64))  
	[`amd64`](https://hub.docker.com/r/amd64/ruby/), [`arm32v5`](https://hub.docker.com/r/arm32v5/ruby/), [`arm32v6`](https://hub.docker.com/r/arm32v6/ruby/), [`arm32v7`](https://hub.docker.com/r/arm32v7/ruby/), [`arm64v8`](https://hub.docker.com/r/arm64v8/ruby/), [`i386`](https://hub.docker.com/r/i386/ruby/), [`ppc64le`](https://hub.docker.com/r/ppc64le/ruby/), [`s390x`](https://hub.docker.com/r/s390x/ruby/)

-	**Published image artifact details**:  
	[repo-info repo's `repos/ruby/` directory](https://github.com/docker-library/repo-info/blob/master/repos/ruby) ([history](https://github.com/docker-library/repo-info/commits/master/repos/ruby))  
	(image metadata, transfer size, etc)

-	**Image updates**:  
	[official-images PRs with label `library/ruby`](https://github.com/docker-library/official-images/pulls?q=label%3Alibrary%2Fruby)  
	[official-images repo's `library/ruby` file](https://github.com/docker-library/official-images/blob/master/library/ruby) ([history](https://github.com/docker-library/official-images/commits/master/library/ruby))

-	**Source of this description**:  
	[docs repo's `ruby/` directory](https://github.com/docker-library/docs/tree/master/ruby) ([history](https://github.com/docker-library/docs/commits/master/ruby))

-	**Supported Docker versions**:  
	[the latest release](https://github.com/docker/docker-ce/releases/latest) (down to 1.6 on a best-effort basis)

# What is Ruby?

Ruby is a dynamic, reflective, object-oriented, general-purpose, open-source programming language. According to its authors, Ruby was influenced by Perl, Smalltalk, Eiffel, Ada, and Lisp. It supports multiple programming paradigms, including functional, object-oriented, and imperative. It also has a dynamic type system and automatic memory management.

> [wikipedia.org/wiki/Ruby_(programming_language)](https://en.wikipedia.org/wiki/Ruby_%28programming_language%29)

![logo](https://raw.githubusercontent.com/docker-library/docs/01c12653951b2fe592c1f93a13b4e289ada0e3a1/ruby/logo.png)

# How to use this image

## Create a `Dockerfile` in your Ruby app project

```dockerfile
FROM winamd64/ruby:2.1-onbuild
CMD ["./your-daemon-or-script.rb"]
```

Put this file in the root of your app, next to the `Gemfile`.

This image includes multiple `ONBUILD` triggers which should be all you need to bootstrap most applications. The build will `COPY . /usr/src/app` and `RUN
bundle install`.

You can then build and run the Ruby image:

```console
$ docker build -t my-ruby-app .
$ docker run -it --name my-running-script my-ruby-app
```

### Generate a `Gemfile.lock`

The `onbuild` tag expects a `Gemfile.lock` in your app directory. This `docker run` will help you generate one. Run it in the root of your app, next to the `Gemfile`:

```console
$ docker run --rm -v "$PWD":/usr/src/app -w /usr/src/app winamd64/ruby:2.1 bundle install
```

## Run a single Ruby script

For many simple, single file projects, you may find it inconvenient to write a complete `Dockerfile`. In such cases, you can run a Ruby script by using the Ruby Docker image directly:

```console
$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp winamd64/ruby:2.1 ruby your-daemon-or-script.rb
```

## Encoding

By default, Ruby inherits the locale of the environment in which it is run. For most users running Ruby on their desktop systems, that means it's likely using some variation of `*.UTF-8` (`en_US.UTF-8`, etc). In Docker however, the default locale is `C`, which can have unexpected results. If your application needs to interact with UTF-8, it is recommended that you explicitly adjust the locale of your image/container via `-e LANG=C.UTF-8` or `ENV LANG C.UTF-8`.

# License

View [license information](https://www.ruby-lang.org/en/about/license.txt) for the software contained in this image.

As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).

Some additional license information which was able to be auto-detected might be found in [the `repo-info` repository's `ruby/` directory](https://github.com/docker-library/repo-info/tree/master/repos/ruby).

As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.
