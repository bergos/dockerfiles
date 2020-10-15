FROM ubuntu:focal

RUN apt-get update && \
  apt-get dist-upgrade -y && \
  apt-get install -y --no-install-recommends \
    python3-pip && \
  pip3 install requests-oauthlib vdirsyncer vdirsyncer[google]

WORKDIR /vdirsyncer

COPY config /vdirsyncer/config

ENTRYPOINT ["/usr/local/bin/vdirsyncer"]
CMD ["-vinfo", "-c", "config", "sync"]
