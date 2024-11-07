FROM ubuntu

ARG URL=https://github.com/hufrea/byedpi/releases/download/v0.15/byedpi-15-x86_64.tar.gz

RUN apt update \
  && apt install -y curl \
  && rm -rf /var/lib/apt/lists/*

COPY rootfs /

RUN mkdir -p /opt/dpi \
  && curl -L $URL | tar xvzf - -C /opt/dpi \
  && ln -s /opt/dpi/ciadpi-x86_64 /opt/dpi/ciadpi

CMD [ "/opt/dpi/ciadpi" ]
