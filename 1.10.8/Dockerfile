FROM m9rco/alpine:3.8
LABEL maintainer="m9rco <pushaowei0727@gmail.com>"
ARG GOLANG_VSERSION=1.10.8-r0

RUN apk add -U --no-cache ca-certificates \
    go=${GOLANG_VSERSION} \
    && rm -rf /var/cache/apk/* 

ENV GOARCH="amd64" \
    GOBIN="" \
    GOCACHE="/root/.cache/go-build" \
    GOEXE="" \
    GOHOSTARCH="amd64" \
    GOHOSTOS="linux" \
    GOOS="linux" \
    GOPATH="/app" \
    GORACE="" \
    GOROOT="/usr/lib/go" \
    GOTMPDIR="" \
    GOTOOLDIR="/usr/lib/go/pkg/tool/linux_amd64" \
    GCCGO="gccgo" \
    CC="gcc" \
    CXX="g++" \
    CGO_ENABLED="1" \
    CGO_CFLAGS="-g -O2" \
    CGO_CPPFLAGS="" \
    CGO_CXXFLAGS="-g -O2" \
    CGO_FFLAGS="-g -O2" \
    CGO_LDFLAGS="-g -O2" \
    PKG_CONFIG="pkg-config" \
    PATH="/usr/bin/go:$PATH" 

ADD rootfs /
ENTRYPOINT ["/sbin/tini", "--"]

CMD ["/bin/sh"]

WORKDIR /app
