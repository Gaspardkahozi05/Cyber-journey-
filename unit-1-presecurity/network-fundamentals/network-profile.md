# Network Profile — [ Kahozi machine]

## Identity
- IPv4 address      :  10.149.136.xxx
- Subnet mask / CIDR:  255.255.255.0
- MAC address       :  2C-9C-58-E2-xx-xx
- Network address   : 10.149.136.0
- Broadcast address :10.149.136.255

## Gateway and reachability
- Default gateway:   10.149.136.148
- - Ping to gateway (avg):57 ms
- Ping to 1.1.1.1 (avg): 41 ms

## DNS
- Configured DNS server(s): 10.149.136.148
- example.com resolves to:   10.149.136.148

## Path to the internet
- Hops to example.com: 8 hops
- First hop: 7 ms     7 ms     6 ms  2001-14bb-690-fc35--22.rev.dnainternet.fi [2001:14bb:690:fc35::22]

## Listening ports
| Port | Protocol | Interface (localhost / all) | Common use |
|------|----------|------------------------------|------------|
| 49673 | TCP | All | Windows dynamic/RPC service |
| 49668 | TCP | All | Windows dynamic/RPC service |
| 49667 | TCP | All | Windows dynamic/RPC service |
| 49666 | TCP | All | Windows dynamic/RPC service |
| 49665 | TCP | All | Windows dynamic/RPC service |
| 49664 | TCP | All | Windows dynamic/RPC service |
| 33683 | TCP | Localhost | Application-specific |
| 32683 | TCP | Localhost | Application-specific |
| 28459 | TCP | All | Application-specific |
| 28451 | TCP | All | Application-specific |
| 26822 | TCP | Localhost | Application-specific |
| 9080 | TCP | Localhost | Web/proxy application |
| 5040 | TCP | All | Windows/application service |
| 139 | TCP | Network interface | NetBIOS Session Service / Windows file sharing |
| 135 | TCP | All | Microsoft RPC Endpoint Mapper |
## Reflection (150–200 words)
- What surprised you about your own network?
What suprised me about my network was that I have alot of ports open that I didnt know about. I didnt really know what ports was before this task.
- Which open port (if any) would you want to investigate or close?
The port I would investigate is port 139 because it is used for Windows file sharing. I would check what is using it before trying to close it.
- Which command do you think you'll use most often, and why?
  The command I would use most is ipconfig /all because it shows my IP adress, gateway, DNS and other network information in one place. It would be useful if I have network problems.
