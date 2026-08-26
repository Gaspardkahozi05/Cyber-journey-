# Packet Tracer - Use Telnet and SSH
<h1>Part 1: Verify Connectivity</h1>
In this part, you will verify that the PC has IP addressing and can ping the remote router.

<h3>Step 1: Verify IP address on a PC.</h3>
- a.     From a PC, click Desktop. Click Command Prompt.

- b.     At the prompt, verify that the PC has an IP address from DHCP.


   <img width="527" height="403" alt="image" src="https://github.com/user-attachments/assets/4e730b8e-198f-44f7-a53e-7cece99bfc5c" />


 <h3>Question:</h3>
- What command did you use to verify the IP address from DHCP?

i used ipconfig /all

<h3>Step 2: Verify connectivity to HQ.</h3>
Verify that you can ping the router HQ using the IP address listed in the Addressing Table.


- <img width="335" height="131" alt="image" src="https://github.com/user-attachments/assets/75330add-3d1c-4466-b213-0f8c9635eb9d" />


<h1>Part 2: Access a Remote Device</h1>
In this part, you will attempt to establish a remote connection using Telnet and SSH.

<h3>Step 1: Telnet to HQ.</h3>
At the prompt, enter the command telnet 64.100.1.1.


- <img width="411" height="44" alt="image" src="https://github.com/user-attachments/assets/7c896878-4485-4746-b865-50673b8acdd1" />


<h3>Question:</h3>
- Were you successful? What was the output?
 no the connection wasn't successful it said"[Connection to 64.100.1.1 closed by foreign host]"

<h3>Step 2: SSH to HQ.</h3>
The router is properly configured to not allow insecure Telnet access. You must use SSH.
At the prompt, enter the command ssh -l admin 64.100.1.1. Enter the password class when prompted.

C:\> ssh -l admin 64.100.1.1

 

- <img width="294" height="73" alt="image" src="https://github.com/user-attachments/assets/14daff18-f755-4224-9608-8d1bafd943b3" />

Password:class

<h3>Question:</h3>
What is prompt after accessing the router successfully via SSH?
after accessing the router the prompt was "HQ#"


