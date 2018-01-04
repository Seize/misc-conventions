# About Go conventions

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).

## Summary

* [Version](#version)
* [Dependencies](#dependencies)
* [Docker](#docker)

# Version

The actual major version is `1.9`.

Your application __MUST__ have a `<app-pkg>.version` variable with default value as `develop`.  
This variable is used to define the version of your application and she is modified at build.

# Dependencies

All dependencies __MUST__ be manage with the [dep](https://github.com/golang/dep) tool.  
You __MUST NOT__ used [glide](https://github.com/Masterminds/glide) or an other tool than [dep](https://github.com/golang/dep).

You __MUST__ commit the `Gopkg.lock` and `Gopkg.toml`.  
You __SHOULD NOT__ commit the `vendor/` directory.

# Docker

You __MUST__ use `golang:1.9-alpine` image to build your application and a `scratch` to run your application.
