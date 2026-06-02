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
  - Confirm the 'serial line fiel'd matches the 'USB serial port'
  - _leave other settings as is. speed should be at 9600_
  - Select 'Open'
  - _console window should open. Press enter key to start session_

# Part 2 (Configure VLANs)
- Name Switch and secure switch
- Create VLANs
  - VLAN 10 - name = TEAM 1
  - VLAN 20 - name = TEAM 2
  - VLAN 30 - name = TEAM 3
- Assign VALNs to Interfaces
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
- *Important* Disable firewalls on both laptops
- On Laptop 2, change the IP settings:
  - IP address        - 192.168.20.10
  - Subnet            - 255.255.255.0
  - Default Gateway   - 192.168.20.1
  - DNS Server        - 8.8.8.8



# Takeaways
I'm glad I purchased this switch. There are just some things a virtual lab doesn't teach. One example is understanding the physical interface layout. 
I assumed the interface layout was horizontal but turns out, it goes vertically. Getting to use the console cable and Putty to connect to the switch was interesting.
It felt liked I was actually on the job. When connecting to the switch via Putty, I did not know that 'Enter' had to be pressed to activate the console screen. Unfortunately,
I ended up waiting for some time before pressing the enter key. Also on the switch, there's a autolock feature that (i dont recall) isnt in Packet Tracer. If inactive for 10 minutes, it locks.





