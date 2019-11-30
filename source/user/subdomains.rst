Subdomains
==========

If you're searching information about a domain, one of the most important
things to do if find which subdomains are defined.

To do that, you can use habu.fqdn.finder, that searchs the valid subdomains
using various techniques:

Zone Transfer
-------------

Every DNS server has a functionality called "zone transfer" that allows to
download the entire "zone file". This is used to synchronize the zones
between various DNS servers.

If this feature is not restricted to the "official" servers only, every
person on the internet can download the entire zone of a domain, with
all the valid subdomains.

This is a vulnerability based on a bad configuration.

habu.fqdn.finder tryies to make a zone transfer as the first thing, because
if it's successful, none of the following techniques are needed.

**Note:** habu.fqdn.finder tryies the zone transfer with the complete list
of name servers for the domain, because sometimes only one of the servers
has the zone transfers publicly available, but this is sufficient to get
the complete zone.


Certificate Transparency Logs
-----------------------------


Certificates On Open Ports
--------------------------


**Note:** Maybe you can think "why check this if you're already checking the
certificate transparency logs?", but the CT log is only useful for certificates
issued by "public" certificate authorities, and a lot of organizations use
self-signed certificates or internal certificate authorities. So, this check is
complementary to the CT log.

  3. Connect to specified ports, obtain SSL certificates and get FQDNs from them


Website links
-------------

  4. Connect to websites and get FQDNs based on the website links


DNS brute force
---------------

  5. DNS Brute Force for common names

