ARG TAG=v1.110
ARG BUILD_DATE=now
ARG GITHUB_SHA_SHORT=working-copy
FROM golang:1-alpine
LABEL \
      org.opencontainers.image.created=$BUILD_DATE \
      org.opencontainers.image.authors="gissehel" \
      org.opencontainers.image.url="https://github.com/gissehel/aroz-dockerize" \
      org.opencontainers.image.documentation="https://github.com/gissehel/aroz-dockerize/blob/$GITHUB_SHA_SHORT/README.md" \
      org.opencontainers.image.source="https://github.com/gissehel/aroz-dockerize" \
      org.opencontainers.image.version=$TAG \
      org.opencontainers.image.revision=$GITHUB_SHA_SHORT \
      org.opencontainers.image.vendor=gissehel \
      org.opencontainers.image.licenses="Open Source" \
      org.opencontainers.image.ref.name="ghcr.io/gissehel/arozos" \
      org.opencontainers.image.title="ArozOS" \
      org.opencontainers.image.description="Image containing latest tag from ArozOS project https://arozos.com/"
RUN \
  apk add git && \
  git clone https://github.com/tobychui/arozos.git /arozos && \
  cd /arozos/src && \
  git checkout $TAG && \
  go build && \
  apk add util-linux ffmpeg
WORKDIR /arozos/src
CMD /arozos/src/arozos -port 80
