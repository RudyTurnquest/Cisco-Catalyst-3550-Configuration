# Cisco-Catalyst-3550-Configuration

# Lab Overview:
Configure a Cisco Catalyst 3550 switch and VLAN implementation

# Equipment used:
- Cisco Catalyst 3550 series switch
- HP Laptops (2)
- Ethernet cables (Cat5a)(2)
- Console cable 
 
# Procedure

# Part 1 (Initial Setup)
- Power on switch 
  - There isn't a power button. To power on, plug the power cable in
- Power on laptop
- Use Console cable to connect the Laptop to the switch
- Confirm serial connection
  - Open Device Manager and expand the "Ports" field
  - Take note of the 'USB serial Port(COM3)' field
  - _(COM3) may be different depending on the device__
- Open "Putty App" on Laptop
  - Select "Serial" for Connection Type
  - Confirm the 'serial line field matches the 'USB serial port'
  - _leave other settings as is. speed should be at 9600_
  - Select 'Open'
  - _console window should open. Press enter key to start session_

# Part 2 (Configure VLANs)
- Name Switch and secure switch
- Create VLANs
  - VLAN 10 - name = TEAM 1
  - VLAN 20 - name = TEAM 2
  - VLAN 30 - name = TEAM 3
- Assign VLANs to Interfaces
  - Ports 1 - 6   - TEAM 1
  - Ports 7 - 12  - TEAM 2
  - Ports 13 -18  - TEAM 3
- Config trunk port on port 24

# Part 3 (Configure SVIs)
- In global config mode, enable ip routing
- Create SVIs
  - establish default gateways for VLANs
  - VLAN 10  -  192.168.10.1
  - VLAN 20  -  192.168.20.1
  - VLAN 30  -  192.168.30.1

# Part 4 (Test VLANs and SVIs)
- Connect laptop 1 to fa0/1 on switch 
- Connect laptop 2 to fa0/12 on switch
- View mac address table
  - To confirm the switch recognizes the both laptops
- View VLAN brief
  - To confirm correct VLAN configuration
- View IP Interface brief
  - To confirm IP addresses are configured correctly on SVIs
- On Laptop 1, change the IP settings:
  - IP address        - 192.168.10.10
  - Subnet            - 255.255.255.0
  - Default Gateway   - 192.168.10.1
  - DNS Server        - 8.8.8.8
- On Laptop 2, change the IP settings:
  - IP address        - 192.168.20.10
  - Subnet            - 255.255.255.0
  - Default Gateway   - 192.168.20.1
  - DNS Server        - 8.8.8.8
- *IMPORTANT* Disable firewalls on both laptops
- From PC1, Ping PC2's gateway
- From PC1, Ping PC2
- From PC2. Ping PC1's gateway
- From PC2, Ping PC1


# Takeaways
I'm glad I purchased the Cisco 3550 as a project to help me prepare for the CCNA and get also get hands on experience. There are just some things a virtual lab doesn't teach. One example is understanding the physical interface layout. 
I assumed the interface layout was horizontal but turns out, it goes vertically. Getting to use the console cable and Putty to connect to the switch was interesting.
It felt liked I was actually on the job. When connecting to the switch via Putty, I did not know that 'Enter' had to be pressed to activate the console screen. Unfortunately,
I ended up waiting for some time before actually pressing the enter key. Also on the switch, there's a auto-lock feature that (i don't recall) isn't in Packet Tracer. If inactive for 10 minutes, it locks. Configuring the device was straight forward
but came to a full stop when I could not ping the PCs. After doing some extensive troubleshooting, I discovered that the firewalls (on both PCs) needed to be disabled. It was a exciting experience and I look forward to doing more labs with this switch.

# Images

1. Switch
<img width="1388" height="1851" alt="Switch" src="https://github.com/user-attachments/assets/b6f392cd-72ae-449b-9118-daca7cdf33f8" />

2. Equipment
<img width="1452" height="1936" alt="Equipment" src="https://github.com/user-attachments/assets/e5cd4ade-4603-4c71-b459-298446a9ecff" />

3. VLAN Configuration
<img width="944" height="632" alt="VLAN config" src="https://github.com/user-attachments/assets/93b1f231-b287-4a70-bb84-e8a637b88245" />

4. SVI Configuration
<img width="803" height="586" alt="SVI config" src="https://github.com/user-attachments/assets/83de6557-ba58-4d19-ae4c-1219c1d8286f" />

5. Verify the Switch sees the PCs
<img width="816" height="588" alt="Mac address confirm" src="https://github.com/user-attachments/assets/4c2b9cc1-ffd3-4b51-a81d-9e3e8eda85fe" />

6. Ping PC2 from PC1
<img width="3024" height="4032" alt="Ping Test 1" src="https://github.com/user-attachments/assets/dea4cc5d-200f-4d4f-b0c8-7b9b78367bb0" />

7. Ping PC1 from PC2
<img width="3024" height="4032" alt="Ping Test 2" src="https://github.com/user-attachments/assets/3f17f9e1-a038-4c11-9852-b5df11d82280" />

























