# Thrift Docker Image

This is repository is fork of [ahawkins/docker-thrift](https://github.com/ahawkins/docker-thrift) that
does not seem to be actively maintained - see [ahawkins/docker-thrift/pull/22](https://github.com/ahawkins/docker-thrift/pull/22).

The new versions, starting with 0.13 are published as `jaegertracing/thrift`. The older versions are available from the official `thrift` organization e.g. `docker pull thrift:0.9.2`.

> The Apache Thrift software framework, for scalable cross-language
> services development, combines a software stack with a code generation
> engine to build services that work efficiently and seamlessly between
> C++, Java, Python, PHP, Ruby, Erlang, Perl, Haskell, C#, Cocoa,
> JavaScript, Node.js, Smalltalk, OCaml and Delphi and other languages.

Read more about [Thrift](https://thrift.apache.org).

# How To Use This Image

This is image is intended to run as an executable. Files are provided
by mounting a directory. Here's an example of compiling
`service.thrift` to ruby.

    docker run -v "$(pwd):/data" jaegertracing/thrift thrift --gen rb /data/service.thrift

# Language Specific Installations

Thrift generates code for many lanuages. Some languages have
additional things to install besides the thrift compiler. They are
listed below:

* Go - `go fmt` from go 1.4

# Build and publish 

```
docker build -f 0.14/Dockerfile  -t jaegertracing/thrift:0.14 .
docker push jaegertracing/thrift:0.14
```
