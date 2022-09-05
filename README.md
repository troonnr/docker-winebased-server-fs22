![FS22](https://raw.githubusercontent.com/wine-gameservers/docker-winebased-server-fs22/main/misc/fs22_top_logo.png "Farming Simulator 22")

# docker-winebased-server-fs22

Farming Simulator 22 server running inside a Docker Container (with [vnc](#vnc)
This project is maintained at [wine-gameservers/docker-winebased-server-fs22](https://github.com/wine-gameservers/docker-winebased-server-fs22) 

Please note this project is missing crucial documentation regarding the usage and requirements for running this docker container, currently this information is only available in our Discord server listed in the footer of this readme.

**Description**

This is the first beta verion to be released!
  
# Table of contents

* [Basic Docker Usage](#basic-docker-usage)
* [System requirements](#system-requirements)
* [Environment Variables](#environment-variables)

* [Configuration](#configuration)

* [vnc](#vnc)

* [Status web server](#status-web-server)


# Basic Docker Usage

```
docker run -d \
    --name docker-fs22-server \
    -p 5900:5900/tcp \
    -p 8080:8080/tcp \
    -p 9000:9000/tcp \
    -p 10823:10823/tcp \
    -p 10823:10823/udp \
    -v /etc/localtime:/etc/localtime:ro \
    -v /path/to/installerfiles:/opt/fs22/installer \
    -v /path/to/gameconfig:/opt/fs22/config \
    -v /path/to/game:/opt/fs22/game \
    -e USERNAME="FS22USER" \
    -e USERID=1000 \
    -e VNC_PASSWORD="FS22USER" \
    -e WEB_USERNAME="FS22USER" \
    -e WEB_PASSWORD="FS22WEBPASSWD" \
    -e RESOLUTION="1280x720" \
    -e SERVER_NAME="FS22 Docker Server" \
    -e SERVER_ADMIN="FS22SERVERADMINPASWD" \
    -e SERVER_PASSWORD="FS22SERVERPASSWD" \
    -e SERVER_PLAYERS="16" \
    -e SERVER_PORT="10823" \
    -e SERVER_REGION="en" \
    -e SERVER_MAP="MapUS" \
    -e SERVER_DIFFICULTY="3" \
    -e SERVER_PAUSE="2" \
    -e SERVER_SAVE_INTERVAL="180.000000" \
    -e SERVER_STATS_INTERVAL="31536000" \
    -e SERVER_CROSSPLAY="true" \
    toetje585/docker-winebased-server-fs22
```

# Environment Variables
**All variable names and values are case-sensitive!**

| Name | Default | Purpose |
|----------|----------|-------|
| `USERNAME` | `FS22USER` | The username used inside the docker container |
| `USERID` | `1000` | The username PUID and GUID |
| `VNC_PASSWORD` | `FS22USER` | Password for connecting using the vnc client |
| `WEB_USERNAME` | `FS22USER` | Username for admin portal at :8080 |
| `RESOLUTION` | `AUTO` | Set a desired screen resolution for the vnc client |
| `SERVER_NAME` | `Docker Server` | Name that will be shown in the server browser |
| `SERVER_PORT` | `10823` | Default: 10823, port that the server will listen on |
| `SERVER_ADMIN` | `FS22USER` | Default: FS22USER, admin username for the game |
| `SERVER_PASSWORD` | `FS22USER` | Default: FS22USER, server password for the game |
| `SERVER_REGION` | `en,de,nl` | One of the following: en, de, jp, pl, cz, fr, es, ru, it, pt, hu, nl, cs, ct, br, tr, ro, kr, ea, da, fi, no, sv, fc |
| `SERVER_PLAYERS` | `16` | Default: 16 amount of players allowed on the server |
| `SERVER_MAP` | `MapUS` | Default: MapUS (Elmcreek), other official maps are: MapFR (Haut-Beyleron), MapAlpine (Erlengrat) |
| `SERVER_DIFFICULTY` | `3` | Default: 3, start from scratch |
| `SERVER_PAUSE` | `2` | Default: 2 Pause the server if no players are connected 1, never pause the server |
| `SERVER_SAVE_INTERVAL` | `180.000000` | Default:180.000000, in seconds |
| `SERVER_STATS_INTERVAL` | `31536000` | Default: 120.000000, webapi is not supported anymore for FS22 so lets give it an odd number so it doesen't spam the logs |
| `SERVER_CROSSPLAY` | `true/false` | Default:true |

# Discord

Want to help or contribute by testing? join my discord!

https://discord.gg/Ejz2MaXSNb

# Legal disclaimer
This Docker container is not endorsed by, directly affiliated with, maintained, authorized, or sponsored by [Giants Software](https://giants-software.com) and [Farming Simulator 22](https://farming-simulator.com/). The logo [Farming Simulator 22](https://giants-software.com) are © 2021 Giants Software.
