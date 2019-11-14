Domain Information
==================

Suppose that you need to obtain information about a domain (this is how many penetration tests starts).

You can use the habu.whois.domain command:

::

   $ habu.whois.domain google.com
   registrar                MarkMonitor, Inc.
   whois_server             whois.markmonitor.com
   creation_date            1997-09-15 04:00:00
   expiration_date          2028-09-14 04:00:00
   name_servers             ns1.google.com, ns2.google.com, ns3.google.com, ns4.google.com
   emails                   abusecomplaints@markmonitor.com, whoisrequest@markmonitor.com
   dnssec                   unsigned
   org                      Google LLC
   country                  US
   state                    CA


Also, remember that you can use the data management commands to obtain specific parts of the data:

::

   $ habu.whois.domain --json google.com | habu.data.select emails
   abusecomplaints@markmonitor.com
   whoisrequest@markmonitor.com


The habu.whois.* commands can output in CSV format, that can be useful to be imported by another tools.

**Note:** JSON is good to be imported on NoSQL databases, and CSV is good for SQL databases).

To know each command available options, please check the command reference or use the '--help' option.

