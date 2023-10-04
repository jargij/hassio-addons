ARG BUILD_FROM
FROM $BUILD_FROM

# Install required inetd as part of busybox-extras
RUN \
  apk add --no-cache \
    busybox-extras \
    wget

WORKDIR /tmp

RUN wget https://raw.githubusercontent.com/Checkmk/checkmk/v2.2.0p10/agents/check_mk_agent.openwrt && \
    chmod +x check_mk_agent.openwrt && \
    mv check_mk_agent.openwrt /usr/local/bin/check_mk_agent

RUN echo "checkmk-agent        6556/tcp   #Checkmk monitoring agent" >> /etc/services

COPY rootfs /

RUN chmod +x /etc/services.d/inetd/run
RUN chmod +x /etc/services.d/inetd/finish