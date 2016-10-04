# coldrye-debian-isc-dhcp-server

[![coldrye/debian-isc-dhcp-server](http://dockeri.co/image/coldrye/debian-isc-dhcp-server)](https://hub.docker.com/r/coldrye/debian-isc-dhcp-server/)


## Description

This packages isc-dhcp-server in various releases based on coldrye/debian-tini.


## Image Releases

Images are released for the following debian releases.

- jessie
- testing

See https://hub.docker.com/r/coldrye/debian-isc-dhcp-server/tags/ for a complete list.


## Environment

- PORT=<UdpPort> (default 67)
- REPLY=<IpAddress> (default 255.255.255.255)
- PROTO=<4|6> (default 4)


## Command

The command is set to ```/usr/sbin/dhcpd -d -p $PORT -$PROTO -s $REPLY -cf /etc/dhcp/dhcpd.conf -tf /etc/dhcp/dhcpd.trace -lf /etc/dhcp/dhcpd.leases.```


## Usage

General Usage

```
touch $(pwd)/data/dhcp/dhcp.leases
docker create --name dhcp -v $(pwd)/data/dhcp:/etc/dhcp --net=host coldrye/debian-isc-dhcp-server:<TAG>
docker start dhcp
```

