FROM ghcr.io/home-assistant/base:latest

# Install required inetd as part of busybox-extras
RUN \
  apk add --no-cache \
    busybox-extras \
    wget

WORKDIR /tmp

RUN wget https://raw.githubusercontent.com/Checkmk/checkmk/refs/heads/release/2.5.0p2/agents/check_mk_agent.openwrt && \
    chmod +x check_mk_agent.openwrt && \
    mv check_mk_agent.openwrt /usr/local/bin/check_mk_agent

RUN echo "checkmk-agent        6556/tcp   #Checkmk monitoring agent" >> /etc/services

COPY rootfs /

RUN chmod +x /etc/services.d/inetd/run
RUN chmod +x /etc/services.d/inetd/finish
