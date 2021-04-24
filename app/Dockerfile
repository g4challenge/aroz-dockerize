ARG TAG=v1.110
FROM golang:1-alpine
RUN \
  apk add git && \
  git clone https://github.com/tobychui/arozos.git /arozos && \
  cd /arozos/src && \
  git checkout $TAG && \
  go build && \
  apk add util-linux ffmpeg
WORKDIR /arozos/src
CMD /arozos/src/arozos -port 80
