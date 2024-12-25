# Topic 1 - IP Addressing :

### cmd 1: ifconfig
```bash
ifconfig
```
Displays active network interface and their IP addresses, Subnet masks and MAC addresses.

```bash
ifconfig -a
```
Lists detailed information about all the network interfaces, including inactive ones.

output :
```bash
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.24.240.76  netmask 255.255.240.0  broadcast 172.24.255.255
        inet6 fe80::215:5dff:fe04:d5b0  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:04:d5:b0  txqueuelen 1000  (Ethernet)
        RX packets 15114  bytes 61383003 (61.3 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 11239  bytes 827892 (827.8 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 60  bytes 7052 (7.0 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 60  bytes 7052 (7.0 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
eth0 - ethernet interface
UP - the interface is active.
BROADCAST - Supports broadcast of packets.
RUNNING - The interface driver is operational.
MULTICAST - Supports multicase communication.

MTU - Maximum transmission Unit (max size of packers in bytes) - default 1500

inet addr - IPv4 adrress 
netmask - indicated the size of subnet, 20 bit network,12 bit host (2^12 = 4096 ips), here 11111111.11111111.11110000.00000000
broadcast - packets sent to this id are delivered to all devices on subnet

inet6 fe80::215:5dff:fe04:d5b0 - IPv6 address
prefixlen 64 - indicates the subnet size
scopeid 0x20<link> - scopeid specifies the scopee of IPv6 address (link means only ont this local link)
    Common scope types include:
        link-local: Valid only on the same physical or logical link (e.g., fe80::/10).
        global: Valid across the entire IPv6 internet.
        site-local (deprecated): Valid only within an administrative domain.

ether 00:15:5d:04:d5:b0 - MAC address
txqueuelen - length of queue for outgoing packets

Packet Statistics: (RX - receive, TX - transmit)

    RX packets 12445 bytes 50759954 (50.7 MB):
        Number of packets (12445) and total data (50.7 MB) received by this interface.
    RX errors 0 dropped 0 overruns 0 frame 0:
        Indicates no errors occurred during reception.
    TX packets 9490 bytes 699021 (699.0 KB):
        Number of packets (9490) and total data (699 KB) transmitted by this interface.
    TX errors 0 dropped 0 overruns 0 carrier 0 collisions 0:
        Indicates no errors occurred during transmission.


lo - loopback (used for internal communication)

flags=73<UP,LOOPBACK,RUNNING>:
Indicates the interface is up and operational, but it’s only for local loopback traffic.

mtu 65536: only used internally.

inet 127.0.0.1:
IPv4 loopback address, commonly referred to as localhost. Traffic sent here stays within the same machine.

inet6 ::1:
IPv6 loopback address (equivalent to 127.0.0.1 for IPv4).

Packet Statistics:

    RX packets 48 bytes 5650 (5.6 KB):
        Traffic received by the loopback interface.
    TX packets 48 bytes 5650 (5.6 KB):
        Traffic sent over the loopback interface.
    No errors or dropped packets are reported, as expected for local traffic.
