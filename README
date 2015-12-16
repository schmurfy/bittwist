This is a private fork that might not be of any use to someone else, the goal is to prepare a trace
recorded on a standard interface to be injected on a loopback interface, here is how I use it:

```bash
# record the trace
tcpdump -plni eth0 -w data.pcap udp and port XXXX


# change destination address
echo "** Change IP destination to 127.0.0.1"
bittwiste -I data.pcap -O fake1.pcap -T ip -d 127.0.0.1

# remove the ethernet header (keep the last two bytes)
echo "** Set link type to loopback"
bittwiste -I fake1.pcap -O fake2.pcap -M 0

echo "** Replacing ethernet header by loopback (with hardcoded IPv4 type)"
bittwiste -I fake2.pcap -O fake3.pcap -Z -D 1-10
```






Original readme:

Bit-Twist: Libpcap-based Ethernet packet generator

Supported platforms:
This distribution is tested to work on Mac OS X 10.6.8

Dependencies:
Libpcap is required (available for download from http://www.tcpdump.org).
This distribution is compiled against libpcap 1.2.1.

Installation:
- tar -xzf bittwist-macosx-2.0.tar.gz (you are most likely to have done this by now)
- cd bittwist-macosx-2.0
- make
- sudo make install
Binaries (bittwist, bittwiste) are installed in /usr/local/bin
Manual pages (bittwist.1, bittwiste.1) are installed in /usr/local/share/man/man1

For more information, please visit Bit-Twist homepage at http://bittwist.sourceforge.net
