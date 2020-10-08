FROM ubuntu:focal

RUN apt-get update && \
  apt-get install -y --no-install-recommends \
    git \
    libauthen-ntlm-perl \
    libclass-load-perl \
    libcrypt-ssleay-perl \
    libdata-uniqid-perl \
    libdigest-hmac-perl \
    libdist-checkconflicts-perl \
    libencode-imaputf7-perl \
    libfile-copy-recursive-perl \
    libfile-tail-perl \
    libio-compress-perl \
    libio-socket-inet6-perl \
    libio-socket-ssl-perl \
    libio-tee-perl \
    libmail-imapclient-perl \
    libmodule-scandeps-perl \
    libnet-dbus-perl \
    libnet-ssleay-perl \
    libpar-packer-perl \
    libreadonly-perl \
    libregexp-common-perl \
    libsys-meminfo-perl \
    libterm-readkey-perl \
    libtest-fatal-perl \
    libtest-mock-guard-perl \
    libtest-mockobject-perl \
    libtest-pod-perl \
    libtest-requires-perl \
    libtest-simple-perl \
    libunicode-string-perl \
    liburi-perl \
    libtest-nowarnings-perl \
    libtest-deep-perl \
    libtest-warn-perl \
    make \
    cpanminus \
    wget && \
  cpanm Mail::IMAPClient && \
  cpanm JSON::WebToken && \
  mkdir /opt/imapsync

WORKDIR /opt/imapsync

RUN wget https://github.com/imapsync/imapsync/archive/imapsync-1.945.tar.gz && \
  tar -xzvf imapsync-1.945.tar.gz && \
  ln -s /opt/imapsync/imapsync-imapsync-1.945/imapsync /usr/bin/

WORKDIR /root

ENTRYPOINT ["/bin/bash"]
