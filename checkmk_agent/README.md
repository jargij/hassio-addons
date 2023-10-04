# Home Assistant Add-on: CheckMK Agent

_Expose CheckMK Agent output on port 6556, so your CheckMK can collect stats and state of your home assistant._

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]
![Supports armv7 Architecture][armv7-shield]
![Supports i386 Architecture][i386-shield]

## About

Checkmk is a comprehensive IT monitoring system that enables system administrators, IT managers, and DevOps teams to identify issues within their infrastructure, including servers, applications, networks, and cloud services. It helps ensure system uptime, performance optimization, and proactive fault resolution.

This add-on is based on the [this forum thread](https://forum.checkmk.com/t/checkmk-agent-on-alpine-linux/21892).

A huge thanks to marass and dnLL for getting the agent to work on HassOS in the first place.

## How to use

Just install and start the container. 
The log should say:
```
[23:23:02] INFO: Starting the inetd daemon...
```

After that you should be able to add your Home Assistant's IP address into CheckMK as normal.

[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg
