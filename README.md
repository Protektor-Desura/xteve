xTeVe 1.9.0 (0083) https://www.xteve.de

Image Maintainer: LeeD hostmaster@dnsforge.com

For support come visit us at our xTeVe Discord channel!: https://discord.gg/eWYquha

xTeVe is a M3U proxy server for Plex, Emby and any client and provider which supports the .TS and .M3U8 streaming formats.

xTeve emulates a SiliconDust HDHomeRun OTA tuner which allows it to expose IPTV style channels to software which would not normally support it.

This image includes the latest version of xTeVe, Guide2go (a Schedules Direct XMLTV grabber), Zap2XML (a Zap2it XMLTV grabber), CROND (to automate XMLTV data retrival) and Perl.

Installation Instructions:

THe recommended settings are listed in the docker run command listed below.

Linux: 

mkdir -p ~/xteve_home 

mkdir -p ~/xteve_tmp

docker run -it -d --name=xteve --network=host --restart=always -e TZ=America/New_York -p 127.0.0.1:34400:34400 -v ~/xteve_home:/home/xteve/conf -v ~/xteve_tmp:/tmp/xteve dnsforge/xteve:latest

Synology:

mkdir /volume1/docker/xteve

mkdir /volume1/docker/xteve_tmp

docker run -it -d --name=xteve --network=host --restart=always -e TZ=America/New_York -p 127.0.0.1:34400:34400 -v /volume1/docker/xteve:/home/xteve/conf -v /volume1/docker/xteve_tmp:/tmp/xteve dnsforge/xteve:latest

Docker run Options:

You can modify the runtime path for specific options.  All you need to do is add them to your docker run command:

TZ         : -e TZ=America/New_York
XTEVE_PORT : -p 127.0.0.1:8080:8080 -e XTEVE_PORT=8080