FROM coldrye/debian-tini:0-9-0-testing-latest

RUN set -ex \
    && export APT_LISTCHANGES_FRONTEND=none \
    && apt-get update \
    && apt-get -q -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" install isc-dhcp-server \
    && apt-get clean \
    && rm -Rf /var/lib/apt/lists/* 2>/dev/null

VOLUME ["/etc/dhcp"]

ENV PORT=67 REPLY=255.255.255.255 PROTO=4

CMD /usr/sbin/dhcpd -d -p $PORT -$PROTO -s $REPLY -cf /etc/dhcp/dhcpd.conf -lf /etc/dhcp/dhcpd.leases -tf /etc/dhcp/dhcpd.trace

