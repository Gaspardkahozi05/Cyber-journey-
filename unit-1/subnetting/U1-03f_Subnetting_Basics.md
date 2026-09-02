# [Subnetting basics]

**Date:** 02-09-2026

**Source:** U1-03f_Subnetting_Basics

**Environment:** windows 

# Task 1 - Binary ↔ decimal for a single octet

Fill in the missing values. Show your work for at least three of them so it's clear you can do the conversion without a calculator.

- 1.1 - Decimal to binary

|Decimal|Binary|
|-------|------|
|10 |00001010|
|210|11010010|
|168|10101000|
|16|00010000|
|255|11111111|
|128|10000000|
|192|11000000|
|248|11111000|
|0|00000000|
<img width="293" height="49" alt="image" src="https://github.com/user-attachments/assets/4b6847dc-e244-40ff-9a0f-a08a5514a247" />


- 1.2 - Binary to decimal


|Binary|Decimal|
|------|-------|
| 11000000| 192|
|11111111 | 255|
| 10101000 | 168|
| 00010000 | 16|
| 11111000 | 248|
| 11010010 | 210|

<img width="296" height="137" alt="image" src="https://github.com/user-attachments/assets/841d16be-4e68-47ce-84da-bf5fa88bfbf5" />

- 1.3 - Full-address conversion

  - IPv4 Addresses in Binary:
  
`10.210.168.16` $\rightarrow$ `00001010.11010010.10101000.00010000`

 `192.168.0.1` $\rightarrow$ `11000000.10101000.00000000.00000001`
 
 `172.16.5.100` $\rightarrow$ `10101100.00010000.00000101.01100100`

  - Binary IPv4 Addresses to Dotted-Decimal:
  
`11000000.10101000.00000001.00000001` $\rightarrow$ `192.168.1.1`

`00001010.00001010.00000000.01001011` $\rightarrow$ `10.10.0.75`

# Task 2 - Recognize the class and CIDR
For each address, name the class (A, B, or C) based on the first octet. Then write the default subnet mask in both dotted-decimal and CIDR notation.

- 2.1 - What Class Is It?

| Address | Class | Default Mask (Dotted) | Default Mask (CIDR) |
| :--- | :--- | :--- | :--- |
| 10.0.0.5 | A | `255.0.0.0` | `/8` |
| 192.168.1.1 | C| `255.255.255.0` | `/24` |
| 172.16.4.20 | B| `255.255.0.0` | `/16` |
| 8.8.8.8| A | `255.0.0.0` | `/8` |
| 200.100.50.25 | C | `255.255.255.0` | `/24` |

- 2.2 - Mask ↔ CIDR ↔ binary
  
| Dotted-Decimal | CIDR | Binary (32 bits) |
|----------------|------|------------------|
| 255.255.255.0|`/24`|`11111111.11111111.11111111.00000000`|
| 255.255.0.0|`/16`| `11111111.11111111.00000000.00000000`|
| 255.0.0.0|`/8`|`11111111.00000000.00000000.00000000` 
| 255.255.255.192|`/26`|`11111111.11111111.11111111.11000000`|
| 255.255.248.0|`/21`|`11111111.11111111.11111000.00000000`|
| 255.255.255.128|`/25`|`11111111.11111111.11111111.10000000`|

- 2.3 - Networks and hosts per class

| Class | Default CIDR | Number of Networks | Number of Hosts per Network |
| :--- | :--- | :--- | :--- |
| A | `/8` | 128 | ~16 Million |
| B| `/16` | 16,384 | 65,534 |
| **C** | `/24` | 2,097,152 | 254 |

# Task 3 - The five key values - the main event
For each of the CIDR blocks below, calculate:

- 3.1 - 172.16.0.0/16
  
Subnet mask `255.255.0.0`

Network address: `172.16.0.0`

Default gateway: `172.16.0.1`

Host range start: `172.16.0.2`

Host range end: `172.16.255.254`

Broadcast:** `172.16.255.255`


- 3.2 - 10.10.0.0/26
  
Subnet mask:`255.255.255.192`

Network address: `10.10.0.0`

Default gateway: `10.10.0.1`

Host range start: `10.10.0.2`

Host range end: `10.10.0.62`

Broadcast: `10.10.0.63`


- 3.3 - 192.168.5.0/28

  
Subnet mask: `255.255.255.240`

Network address: `192.168.5.0`

Default gateway: `192.168.5.1`

Host range start: `192.168.5.2`

Host range end: `192.168.5.14`

Broadcast: `192.168.5.15`


- 3.4 - 10.0.0.0/30
  
Subnet mask: `255.255.255.252`

Network address: `10.0.0.0`

Default gateway: `10.0.0.1`

Host range start:`10.0.0.2`

Host range end: `10.0.0.2`

Broadcast: `10.0.0.3`


- 3.5 - 192.168.100.128/25
  
Subnet mask: `255.255.255.128`

Network address: `192.168.100.128`

Default gateway: `192.168.100.129`

Host range start: `192.168.100.130`

Host range end: `192.168.100.254`

Broadcast: `192.168.100.255`





# How I calculated it:
First, I looked at the /24.
32 - 24 = 8 host bits
So there are 8 bits available for devices.
Then I calculated the number of addresses:
2^8 = 256 addresses
We cannot use 2 of these addresses:
- one is for the network(the first ip)
- one is for the broadcast(the last Ip)
  
So:
256 - 2 = 254 usable hosts
Now I find the subnet mask.
A /24 means the first 24 bits are for the network:
11111111.11111111.11111111.00000000

# Task 4 - Which subnet does this host belong to?

For each host address, work out the network address of the subnet it sits in. Show your work - the trick is to look at where the mask boundary falls in the relevant octet.

### 4.1 Host: 10.10.0.75/26
* **Network address:** `10.10.0.64`
* **Broadcast address:** `10.10.0.127`
* **Is this a valid host IP?** **Yes**, because `.75` falls between `.65` and `.126`.

### 4.2 Host: 192.168.1.200/26
* **Network address:** `192.168.1.192`
* **Broadcast address:** `192.168.1.255`
* **Is this a valid host IP?** **Yes**, because `.200` falls between `.193` and `.254`.

### 4.3 Host: 172.16.5.130/25
* **Network address:** `172.16.5.128`
* **Broadcast address:** `172.16.5.255`
* **Is this a valid host IP?** **Yes**, because `.130` falls between `.129` and `.254`.

### 4.4 Host: 10.0.0.0/30
* **Network address:** `10.0.0.0`
* **Broadcast address:** `10.0.0.3`
* **Is this a valid host IP?** **No**, because `.0` is the **Network Address** itself and cannot be given to a device.

# Task 5 - Slicing up a /24
You've been given the network 192.168.10.0/24 and need to divide it into smaller subnets for four departments.

* **Subnet 1:**
  * Network: `192.168.10.0`
  * Gateway: `192.168.10.1`
  * Host Range: `192.168.10.2` – `192.168.10.62`
  * Broadcast: `192.168.10.63`

* **Subnet 2:**
  * Network: `192.168.10.64`
  * Gateway: `192.168.10.65`
  * Host Range: `192.168.10.66` – `192.168.10.126`
  * Broadcast: `192.168.10.127`

* **Subnet 3:**
  * Network: `192.168.10.128`
  * Gateway: `192.168.10.129`
  * Host Range: `192.168.10.130` – `192.168.10.190`
  * Broadcast: `192.168.10.191`

* **Subnet 4:**
  * Network: `192.168.10.192`
  * Gateway: `192.168.10.193`
  * Host Range: `192.168.10.194` – `192.168.10.254`
  * Broadcast: `192.168.10.255`

# 5.2 Subnet Size Optimization


| CIDR | Total IPs | Usable Hosts (Total - 2) |
| :--- | :--- | :--- |
| **/24** | 256 | 254 |
| **/25** | 128 | 126 |
| **/26** | 64 | **62** |
| **/27** | 32 | **30** |
| **/28** | 16 | **14** |
| **/29** | 8 | **6** |
| **/30** | 4 | **2** |

# Task 6 - IPv6, briefly
IPv6 addresses are 128 bits long - four times as long as IPv4. They're written as 8 groups of 4 hex digits separated by colons.

**### 6.1 Hex to Decimal to Binary

| Hex | Decimal | Binary (4 bits) |
| :--- | :--- | :--- |
| **0** | 0 | `0000` |
| **5** | 5 | `0101` |
| **a** | 10 | `1010` |
| **f** | 15 | `1111` |

---

### 6.2 Compressed IPv6 Addresses

1. `2001:0df8:23f2:0000:0000:0000:0000:0f11`  
   **Compressed:** `2001:df8:23f2::f11`

2. `2001:0000:00d0:00f2:0000:0000:0000:0f11`  
   **Compressed:** `2001:0:d0:f2::f11`

3. `fe80:0000:0000:0000:0000:0000:0000:0001`  
   **Compressed:** `fe80::1`**

### 6.3 Why Do We Need IPv6?

IPv4 has about 4.3 billion IP addresses, but there are so many phones, computers, and other devices connected to the internet that we are running out of addresses. IPv6 uses 128-bit addresses, which gives us a huge number of new IP addresses. This means there are enough addresses for all the devices we need to connect to the internet.

<img width="686" height="538" alt="image" src="https://github.com/user-attachments/assets/1b03e9a3-14f2-4616-851d-803c1d2b766c" />



