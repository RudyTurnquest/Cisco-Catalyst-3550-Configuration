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

# Part 2 (Configure Switch)
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

# Part 3 (Test VLANs)
- Connect 1 laptop to port 1 on switch 
- Connect other laptop to port 2 on switch
- Confirm on Switch that the two laptops are in the same VLAN

# Takeaways




