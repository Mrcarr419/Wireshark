# Wireshark
Wireshark filter and inspect a packet
Here im inpecting Packets using wireshark

<img width="1440" alt="Screenshot 2024-09-13 at 12 40 18 AM" src="https://github.com/user-attachments/assets/45ecc074-bd01-4741-a47c-71303134733a">

Checking for Echo pings

Input (ip.addr == 142.250.1.139) to reduce information and contains only packets where either the source or the destination IP address matches the address. Now only two packet colors are used: light pink for ICMP protocol packets and light green for TCP (and HTTP, which is a subset of TCP) packets.

<img width="1440" alt="Screenshot 2024-09-13 at 1 04 10 AM" src="https://github.com/user-attachments/assets/984d7f22-4aa5-4e20-a46a-d2088bc82ba4">

The lower section of the window contains the raw packet data displayed in hexadecimal and ASCII text. There is also placeholder text for fields where the character data does not apply, as indicated by the dot (“.”).

<img width="1440" alt="Screenshot 2024-09-13 at 1 11 47 AM" src="https://github.com/user-attachments/assets/6e100ad6-4c0e-458c-b9b3-981639dd7197">

This displays the frame length and the arrival time of the packet. This is information about the entire packet of data.

<img width="1440" alt="Screenshot 2024-09-13 at 1 18 47 AM" src="https://github.com/user-attachments/assets/56fe30d8-ae0b-4e30-b6d0-17880767a6af">

Checking the ethernet level, this shows the source and destination MAC addresses and the type of internal protocol that the Ethernet packet contains.

<img width="1440" alt="Screenshot 2024-09-13 at 1 21 51 AM" src="https://github.com/user-attachments/assets/c6173cd6-da72-4639-9a98-22eaf3d0d7b5">

The Internet Protocol (IP) data contained in the Ethernet packet. It contains information such as the source and destination IP addresses and the Internal Protocol (TCP or UDP), which is carried inside the IP packet.

<img width="1440" alt="Screenshot 2024-09-13 at 1 25 51 AM" src="https://github.com/user-attachments/assets/cbe57bfe-5ab7-4e2e-836a-b42d6b28b433">

Transmission Control Protocol subtree.
This provides detailed information about the TCP packet, including the source and destination TCP ports, the TCP sequence numbers, and the TCP flags.

<img width="1440" alt="Screenshot 2024-09-13 at 1 28 03 AM" src="https://github.com/user-attachments/assets/8242843f-2d9c-42c9-8c0e-6cc6d03db537">

Now I'm searching through udp.port == 53

Domain Name System (query) subtree to expanded it, Scrolled down and double tapped Queries. The Query that was looked at was (139.1.250.142.in-addr.arpa: type PTR, class IN)
the website that was queried is (opensource.google.com.)
<img width="1440" alt="Screenshot 2024-09-13 at 1 35 05 AM" src="https://github.com/user-attachments/assets/3686b6d1-0d7d-410a-b4be-0163340f0782">

Now im checking (tcp.port == 80) time to live in which is 64

<img width="1440" alt="Screenshot 2024-09-13 at 1 48 52 AM" src="https://github.com/user-attachments/assets/c303fa1d-c49a-44a3-a2e4-8fb357228b37">

now im checking (tcp.port == 80)
Quite a few packets were created when the user accessed the web page (http://opensource.google.com.)
 Time to Live value of the packet as specified in the Internet Protocol Version 4 subtree is (64),  the frame length is (54) and the header lengrh is 20 bytes.

<img width="1440" alt="Screenshot 2024-09-13 at 2 04 09 AM" src="https://github.com/user-attachments/assets/41aed914-9350-44b8-b20d-01efa5613fea">

The Destination Address as specified in the Internet Protocol Version 4 subtree (169.254.169.254)

<img width="1440" alt="Screenshot 2024-09-13 at 2 09 40 AM" src="https://github.com/user-attachments/assets/a5db222e-72ea-4e28-a69c-277149c006cf">

Now I'm searching for data that presents 'Curl'
This filters to packets containing web requests made with the curl command in this packet capture file.

<img width="1440" alt="Screenshot 2024-09-13 at 2 12 10 AM" src="https://github.com/user-attachments/assets/66f6afcd-f871-4b80-8434-9c8ad3fcc906">

