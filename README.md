# print-iptables-logs
Print the iptables logs on all the chains

How to track the linux packet in the kernel through iptables.

use the below commands:

iptables -t mangle -I PREROUTING --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix MANGLE-PRE::

iptables -t nat -I PREROUTING --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix NAT-PRE::

iptables -t mangle -I INPUT --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix MANGLE-INPUT::

iptables -t mangle -I FORWARD --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix MANGLE-FORWARD::

iptables -t mangle -I OUTPUT --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix MANGLE-OUTPUT::

iptables -t mangle -I POSTROUTING --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix MANGLE-POST::

iptables -t nat -I INPUT --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix NAT-INPUT::

iptables -t nat -I OUTPUT --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix NAT-OUTPUT::

iptables -t nat -I POSTROUTING --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix NAT-POST::

iptables -t filter -I INPUT --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix FILTER-INPUT::

iptables -t filter -I FORWARD --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix FILTER-FORWARD::

iptables -t filter -I OUTPUT --protocol tcp --tcp-flags FIN FIN -j LOG --log-prefix FILTER-OUTPUT::
