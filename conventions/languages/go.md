# About Go conventions

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).

## Summary

* [Version](#version)
* [Dependencies](#dependencies)
* [Docker](#docker)

# Version

The actual major version is `1.10`.

Your application __MUST__ have `<app-pkg>.version`,  `<app-pkg>.gitCommit` and  `<app-pkg>.built` (RFC3339 date) variables with default value as `0.0.0`, `dev` and "".  
This variable is used to define the version of your application and she is modified at build.

_Example:_
```go
package main

var (
	version   = "0.0.0"
	gitCommit = "dev"
	built     = ""
)
```

# Dependencies

All dependencies __MUST__ be manage with the [dep](https://github.com/golang/dep) tool.  
You __MUST NOT__ used [glide](https://github.com/Masterminds/glide) or an other tool than [dep](https://github.com/golang/dep).

You __MUST__ commit the `Gopkg.lock` and `Gopkg.toml`.  
You __SHOULD NOT__ commit the `vendor/` directory.

# Docker

You __MUST__ use `golang:1.10.0-alpine3.7` image to build your application and a `scratch` to run your application.

_Example:_

```dockerfile
# Builder
FROM golang:1.10-0-alpine3.7 as builder
# ...
RUN CGO_ENABLED=0 GOOS=linux go build -ldflags "..." -a -installsuffix cgo -o app .

# Application
FROM scratch
# ...
COPY --from=builder /go/src/.../app .
# ...
```
