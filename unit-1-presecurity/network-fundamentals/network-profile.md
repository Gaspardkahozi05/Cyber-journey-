# Network Profile — [ Kahozi machine]

## Identity
- IPv4 address      :  10.149.136.xxx
- Subnet mask / CIDR:  255.255.255.0
- MAC address       :  2C-9C-58-E2-xx-xx
- Network address   : 10.149.136.0
- Broadcast address :10.149.136.255
  
- Q3: What is the difference between your IP address and your MAC address? Which one can change, and which one is (mostly) fixed to your hardware? Which one operates at which OSI layer?
  
The IP address can change depending on the network, while the MAC address is mostly fixed to the network hardware. IP addresses operate at OSI Layer 3 (Network), while MAC addresses operate at OSI Layer 2 (Data Link).


- Q4: Your subnet mask is most likely 255.255.255.0, which is written as /24 in CIDR notation.
- How many total addresses does a /24 contain?
- How many of those are usable for devices (after subtracting the network and broadcast addresses)?
- If your IP is 192.168.1.37/24, what is the network address and what is the broadcast address?

Total addresses: 256
Usable device addresses: 254
Example IP: 192.168.1.37/24
Network address: 192.168.1.0
Broadcast address: 192.168.1.255

## Gateway and reachability
- Default gateway:   10.149.136.148
- Ping to gateway (avg):57ms
- Ping to 1.1.1.1 (avg): 65ms
- Q6: What was the average round-trip time to your gateway versus to 1.1.1.1? Why is one much faster than the other?
  
the default gate way is faster because it belongs the local nework

- Q7: Now try ping -c 4 example.com (or -n 4 on Windows). It worked using a name instead of an IP address. What service made that possible? (This leads into Part 3.)
  
DNS (Domain Name System) made it possible to use a domain name
    

## DNS
- Configured DNS server(s): 10.149.136.148
- example.com resolves to:   10.149.136.148

- Q10: A security thought: DNS lookups are usually sent in cleartext. If someone could watch your network traffic, what could they learn about you just from your DNS queries — even if all the websites you visit use HTTPS?
  
Someone monitoring my network traffic could potentially see the domain names I am looking up and use that information to learn which websites or online services I am accessing, even when the actual websites use HTTPS.

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

- Q14: Look up what two of these ports are commonly used for (a quick web search for "port 22" or "port 445" is fine). Why does it matter, from a security standpoint, whether a port is listening on localhost only versus on all interfaces?

Port 135: Windows RPC (Remote Procedure Call)
Port 139: Windows NetBIOS Session Service, commonly associated with Windows file and printer sharing
- Q15: A security thought: an attacker scanning your machine sees only the ports listening on 0.0.0.0 (network-facing), not the localhost-only ones. Based on your output, is your machine exposing more or fewer network-facing services than you expected?

My machine is exposing more network-facing services than I expected, with 11 ports listening.

## Reflection (150–200 words)
- What surprised you about your own network?

  What suprised me about my network was that I have alot of ports open that I didnt know about. I didnt really know what ports was before this task. 

- Which open port (if any) would you want to investigate or close?

The port I would investigate is port 139 because it is used for Windows file sharing. I would check what is using it before trying to close it.


- Which command do you think you'll use most often, and why?

  The command I would use most is ipconfig /all because it shows my IP adress, gateway, DNS and other network information in one place. It would be useful if I have network problems.
