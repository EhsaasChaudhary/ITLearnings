# IP Addressing

## Command: `ifconfig`

### Usage

- **`ifconfig`**: Displays active network interfaces along with their IP addresses, subnet masks, and MAC addresses.
- **`ifconfig -a`**: Lists detailed information about all network interfaces, including inactive ones.

### Example Output

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
## Key Components of `ifconfig` Output

### `eth0` - Ethernet Interface

- **Flags**: Indicates the interface state and capabilities.
  - **UP**: The interface is active.
  - **BROADCAST**: Supports broadcast of packets.
  - **RUNNING**: The interface driver is operational.
  - **MULTICAST**: Supports multicast communication.
- **MTU (Maximum Transmission Unit)**: Maximum size of packets (in bytes). Default is 1500.

## IPv4 Information

- **`inet`**: IPv4 address of the interface (e.g., `172.24.240.76`).
- **`netmask`**: Subnet mask, indicating the size of the subnet. For example:
  - `255.255.240.0` represents a 20-bit network and a 12-bit host (2^12 = 4096 IPs).
  - **Binary**: `11111111.11111111.11110000.00000000`.
- **`broadcast`**: Address to broadcast packets to all devices on the subnet.

## IPv6 Information

- **`inet6`**: IPv6 address of the interface (e.g., `fe80::215:5dff:fe04:d5b0`).
- **`prefixlen`**: Subnet size (e.g., `64`).
- **`scopeid`**: Specifies the scope of the IPv6 address:
  - **link**: Valid only on the same physical or logical link (e.g., `fe80::/10`).
  - **global**: Valid across the entire IPv6 internet.

## MAC Address

- **`ether`**: MAC address of the interface (e.g., `00:15:5d:04:d5:b0`).

## Transmission Queue

- **`txqueuelen`**: Length of the queue for outgoing packets.

## Packet Statistics

```bash
RX packets 12445 bytes 50759954 (50.7 MB):
Number of packets (12445) and total data (50.7 MB) received by this interface.

RX errors 0 dropped 0 overruns 0 frame 0:
Indicates no errors occurred during reception.

TX packets 9490 bytes 699021 (699.0 KB):
Number of packets (9490) and total data (699 KB) transmitted by this interface.

TX errors 0 dropped 0 overruns 0 carrier 0 collisions 0:
Indicates no errors occurred during transmission.
```

### RX (Receive)

- **Packets**: Number of packets received.
- **Bytes**: Total data received.
- **Errors, Drops, Overruns, Frame**: Error statistics.

### TX (Transmit)

- **Packets**: Number of packets transmitted.
- **Bytes**: Total data transmitted.
- **Errors, Drops, Overruns, Carrier, Collisions**: Error statistics.


## Loopback Interface (lo):

Used for internal communication within the system.

### Flags
- UP
- LOOPBACK
- RUNNING

### MTU (Maximum Transmission Unit):
- 65536 (used internally)

### IPv4 Loopback:
- **inet**: 127.0.0.1 (commonly referred to as localhost.)
  - Traffic sent here stays within the same machine.

### IPv6 Loopback:
- **inet6**: ::1 (equivalent to 127.0.0.1 for IPv4)

## Packet Statistics:
```bash
RX packets 48 bytes 5650 (5.6 KB):
Traffic received by the loopback interface.

TX packets 48 bytes 5650 (5.6 KB):
Traffic sent over the loopback interface.
```
- **RX (Receive)**: Traffic received by the loopback interface.
- **TX (Transmit)**: Traffic sent over the loopback interface.

No errors or dropped packets are reported, as expected for local traffic.
