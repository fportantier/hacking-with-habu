First Steps with Habu
=====================

Habu has a lot of commands that are named with the following format:

habu.<namespace>.<command>

So, you can get the complete list of commands using the tab completion feature of all shells.

::

   $ habu.<TAB><TAB>
   habu.arp.ping            habu.config.set          habu.decrypt.gppref      habu.extract.hostname    habu.http.headers        habu.karma               habu.select              habu.usercheck
   habu.arp.poison          habu.config.show         habu.dhcp.discover       habu.extract.ipv4        habu.http.options        habu.karma.bulk          habu.server.ftp          habu.vhosts
   habu.arp.sniff           habu.contest             habu.dhcp.starvation     habu.fernet              habu.interfaces          habu.land                habu.shodan              habu.virustotal
   habu.asydns              habu.crack.luhn          habu.dns.lookup.forward  habu.fernet.genkey       habu.ip                  habu.nc                  habu.shodan.open         habu.web.report
   habu.b64                 habu.crack.snmp          habu.dns.lookup.reverse  habu.filter              habu.ip2asn              habu.nmap.excluded       habu.shodan.query        habu.web.screenshot
   habu.cert.clone          habu.crtsh               habu.eicar               habu.forkbomb            habu.ip.geolocation      habu.nmap.open           habu.synflood            habu.web.tech
   habu.certclone           habu.cve.2018.9995       habu.expand              habu.gateway.find        habu.ip.internal         habu.nmap.ports          habu.tcpflags            habu.whois.domain
   habu.cert.names          habu.cymon.ip            habu.extract.domain      habu.hasher              habu.isn                 habu.ping                habu.tcpscan             habu.whois.ip
   habu.config.del          habu.cymon.ip.timeline   habu.extract.email       habu.host                habu.jshell              habu.protoscan           habu.traceroute          habu.xor


Command names and namespaces can change, so, trust in the list printed by your own execution.

The reason to use namespaces is to organize the commands and make easy to find them.

