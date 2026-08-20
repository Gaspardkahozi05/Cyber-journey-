# [Wireshark - Cleartext vs Encrypted Traffic]

**Date:** 20226-08-20
**Source:** (U1-03a Assignment wireshark network control)
**Environment:** (windows pc)

## Goal
- to Observe the difference between unencrypted and encrypted network traffic in a real packet capture, and recognize why protocol choice matters for confidentiality.
  
- look at both and notice what an eavesdropper on the network could — and could not — see in each case.

## Steps
- firstly i installed wireshark on my pc
  
- then downloaded the wireshark files provided by the teacher which Both capture files record the same login to the same fictional lab web application


## Findings
## Part A — the HTTP capture (U1-03a_http_login.pcap)

1. Find the login submission. What username and password were sent? Paste the line from the stream where you found them.

- username = anna.virtanen
- password = Summer2026!&remember=on
- Line = 1	0.000000	10.10.10.50	10.10.10.10	TCP	54	49788 → 80 [SYN] Seq=0 Win=64240 Len=0

 
2. The login form was submitted using which HTTP method — GET or POST? (Look at the packet that carries the credentials.)
   
- GET was used
  
3. After a successful login, the server sends back a Set-Cookie header. What is the value of the SESSIONID cookie? Why might an attacker who sees this cookie be dangerous, even without the password?

 - Set-Cookie: SESSIONID=a3f9c2e7b81d4f60a5e2c9d10f4b7e88
 
 -   The server may use the SESSIONID as proof that the browser has already logged in, so the attacker could potentially make authenticated requests without knowing the user's password  

4. The dashboard page (the final server response) reveals personal details about the user. List two pieces of sensitive information visible there.

- <!DOCTYPE html><html><head><title>Dashboard</title></head><body> h1>Welcome back, Anna Virtanen</h1><p>Role: Finance Administrator</p><p>Email: anna.virtanen@pohjola-logistics.local</p><p>Last login from 10.10.10.50</p></body></html>

## Part B — the HTTPS capture (U1-03a_https_login.pcap)
5. Apply the filter tls. Can you find the username and password anywhere in this capture? Why or why not?

- I could not find any details
-because https is encrypted and http is not encrypted 

6. Look at the first TLS packet (the "Client Hello"). One piece of plaintext is still visible here: the name of the server the client is connecting to. What is it? (Hint: look for "Server Name" / SNI in the packet details.)

- the server name is lab-portal.local

7. Even though the contents are encrypted, name one thing an eavesdropper can still learn from the HTTPS capture (think about addresses, timing, or sizes).
- IP address
- timing
- server name and IP
## Part C — making sense of it

8. In one sentence: why does the protocol choice (HTTP vs HTTPS) matter for confidentiality?
- https is more secure and encrypted than httpt there for always use https for confidentiality

9. Name one situation in your daily life where you might be sending traffic over an untrusted network (e.g. public Wi-Fi). What protects you, and what would still be exposed?
- I am a little weird about my privacy i thing like every time i access a website then someone is listen so i always use a vpn so my IP and location won't be exposed

  
## Issues and how I resolved them
- no issues with this assignment everything was good but i also got  a little help from A.I just to understand more better

## References
we just had two wireshark files provided by the teacher
