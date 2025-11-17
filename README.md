# Ex. No: 11 – Packet Tracer: Verify IPv4 and IPv6 Addressing
# Date: 14-11-2025
________________________________________<br>
# Objective
To configure, verify, and test dual-stack (IPv4 and IPv6) addressing on a Cisco Packet Tracer network topology.<br>
Tasks:<br>
• Document IPv4 and IPv6 addressing details.<br>
• Test connectivity using ping for both protocols.<br>
• Trace the route of packets to verify end-to-end connectivity.<br>
________________________________________<br>
# Apparatus / Tools Required
• Cisco Packet Tracer<br>
• 3 Routers (R1, R2, R3 – 2911 or equivalent)<br>
• 2 PCs (PC1, PC2)<br>
• Copper straight-through and Serial DCE/DTE cables<br>
________________________________________<br>
# Network Topology Diagram
![4269834c-fb34-41d5-935f-0bc43a4b5a28](https://github.com/user-attachments/assets/456b9bf2-64b4-4503-93ef-7edf0ded6f84)

________________________________________<br>
# Addressing Table
Device	Interface	IPv4 Address / Subnet Mask	IPv6 Address / Prefix	Default Gateway<br>
R1	G0/0	10.10.1.97 / 255.255.255.224	2001:db8:1:1::1/64	N/A<br>
R1	S0/0/1	10.10.1.6 / 255.255.255.252	2001:db8:1:2::2/64	N/A<br>
R2	S0/0/0	10.10.1.5 / 255.255.255.252	2001:db8:1:2::1/64	N/A<br>
R2	S0/0/1	10.10.1.9 / 255.255.255.252	2001:db8:1:3::1/64	N/A<br>
R3	G0/0	10.10.1.17 / 255.255.255.240	2001:db8:1:4::1/64	N/A<br>
R3	S0/0/1	10.10.1.10 / 255.255.255.252	2001:db8:1:3::2/64	N/A<br>
PC1	NIC	(IPv4 auto/DHCP)	(IPv6 auto-config)	R1 G0/0<br>
PC2	NIC	(IPv4 auto/DHCP)	(IPv6 auto-config)	R3 G0/0<br>
________________________________________
# Procedure
# Part 1: Verify IPv4 and IPv6 Addressing
1.	On PC1, open Command Prompt → enter:<br>
2.	ipconfig /all<br>
Record IPv4 address, subnet mask, and gateway.<br>
3.	On PC2, repeat the same.<br>
4.	For IPv6 verification:<br>
5.	ipv6config /all<br>
Record IPv6 address, prefix, and default gateway for both PCs.<br>
________________________________________<br>
# Part 2: Test Connectivity Using Ping
1.	From PC1, ping the IPv4 address of PC2.<br>
2.	ping 10.10.1.20<br>
o	Verify success (Reply from 10.10.1.20).<br>
3.	From PC2, ping the IPv6 address of PC1.<br>
4.	ping 2001:db8:1:1::a<br>
o	Verify success for IPv6 reachability.
________________________________________<br>
# Part 3: Discover the Path Using Traceroute
1.	From PC1, trace route to PC2 using IPv4:<br>
2.	tracert 10.10.1.20<br>
Observe the hops across R1 → R2 → R3.<br>
3.	From PC2, trace route to PC1 using IPv6:<br>
4.	tracert 2001:db8:1:4::a<br>
Record IPv6 path hops.<br>
________________________________________<br>
# Commands Used (Summary)
Purpose	Command<br>
Check IPv4 details	ipconfig /all<br>
Check IPv6 details	ipv6config /all<br>
Ping test (IPv4/IPv6)	ping <IP><br>
Trace path (IPv4/IPv6)	tracert <IP><br>
________________________________________<br>
# Verification & Testing
• Successful ping replies indicate proper dual-stack connectivity.<br>
• Trace route confirms correct path through routers R1–R2–R3.<br>
________________________________________
# Output (Attach Screenshots)
• ipconfig /all and ipv6config /all output for both PCs.<br>
![4792b21c-9875-42ec-8382-b950642864d1](https://github.com/user-attachments/assets/8ea47497-94dd-4d86-b4a0-617c7f1eac91)
![041295b4-7f70-40b7-b718-df697c7cfd96](https://github.com/user-attachments/assets/40f0b9f1-ba3f-46a4-9a0c-dc3641c538ca)
![e38f0cfe-e302-4fc3-a6e8-ad0f8d06858e](https://github.com/user-attachments/assets/a1be84b7-b603-4bc2-ad83-0ee271f7524c)

• Ping results for IPv4 and IPv6.<br>
![63cf14fe-f86b-4f9d-99ec-82e6c2743ed3](https://github.com/user-attachments/assets/97af73b3-a6f5-4afb-bf93-6b0e01399f92)

• Traceroute results showing intermediate hops.<br>
_![0415c89b-9811-4468-8216-28dcfa72a936](https://github.com/user-attachments/assets/83fc9bac-6afc-4a36-baa9-8110b204ecd3)

![14d51053-09ac-4954-8586-147cbb1b97e4](https://github.com/user-attachments/assets/9816fe73-b1b1-4ce3-bf75-b776d5710cbb)
<img width="1918" height="1018" alt="Screenshot 2025-11-14 094334" src="https://github.com/user-attachments/assets/0866b255-5430-44c1-9c1c-f0954dd4fe10" />
____________________________________
# Result
The dual-stack IPv4 and IPv6 addressing scheme was successfully verified. Both addressing types achieved full connectivity between PC1 and PC2 through multiple routers, confirming correct configuration and routing.

