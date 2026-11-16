# ARP Investigation – Practical 01

## 1. Aim

To examine the ARP table and understand how a computer maps IP addresses to MAC addresses and identifies devices on a local network.

## 2. Theory

**What is ARP?**

ARP (Address Resolution Protocol) helps a computer find the MAC address associated with an IP address on a local network.

**Important Concepts:**

- **IP Address:** A logical address used to identify a device on a network.
- **MAC Address:** A hardware network address used to identify a device on a local network.
- **ARP Table:** A record that stores IP-to-MAC address mappings.
- **Dynamic Entry:** An entry automatically learned through ARP communication.
- **Static Entry:** An entry manually configured or predefined rather than dynamically learned.
- **ARP Spoofing:** An attack where an attacker sends fake ARP messages to associate their MAC address with another device's IP address.

### Types of Network Communication

- **Unicast:** Communication between one sender and one receiver.
- **Broadcast:** Communication sent to all devices on a local network.
- **Multicast:** Communication sent to a selected group of devices.

## 3. Commands Performed

### Command 1: Display the ARP Table

```cmd
C:\Windows\System32\arp.exe -a
```

**Purpose:** Displays the ARP cache containing IP addresses, corresponding MAC addresses and entry types for available network interfaces.

### Command 2: Display Network Configuration

```cmd
C:\Windows\System32\ipconfig.exe /all
```

**Purpose:** Displays detailed network configuration, including IPv4 addresses, MAC addresses, subnet masks, default gateways and DHCP information.

### Command 3: Filter the ARP Table

```cmd
C:\Windows\System32\arp.exe -a -N 192.168.0.106
```

**Purpose:** Displays ARP entries associated with the specified Wi-Fi network interface.

### Command 4: Test Network Connectivity

```cmd
C:\Windows\System32\PING.EXE 192.168.0.1
```

**Purpose:** Sends test packets to the default gateway to check network connectivity and measure response time.

### Command 5: Verify ARP Entries

```cmd
C:\Windows\System32\arp.exe -a -N 192.168.0.106
```

**Purpose:** Rechecks the ARP table after network communication to observe the router's IP-to-MAC mapping.

## 4. Observations

The following observations were recorded during the practical:

1. Three network interfaces were identified: Wi-Fi, VMware VMnet1 and VMware VMnet8.
2. The active Wi-Fi interface had the IPv4 address `192.168.0.106`.
3. The default gateway was identified as `192.168.0.1`.
4. The router's MAC address was found to be `d4-6e-0e-b1-09-2c`.
5. The router appeared as a dynamic entry in the ARP table.
6. Broadcast and multicast entries appeared as static entries.
7. The ping test successfully received all four packets with 0% packet loss.
8. The router's IP-to-MAC mapping remained present after the connectivity test.

## 5. Key Learnings

- Understood how ARP resolves IP addresses into MAC addresses.
- Learned how to inspect and filter the ARP cache.
- Identified different network interfaces and their configurations.
- Understood the difference between dynamic and static ARP entries.
- Learned how broadcast, multicast and unicast communication differ.
- Understood how ARP spoofing can manipulate IP-to-MAC mappings.

## 6. Result

Successfully inspected and analysed the ARP table, identified network interfaces, examined IP-to-MAC address mappings and verified router connectivity using the ping command.

The practical provided an understanding of how ARP operates and how its mappings relate to network security.

---

**Tools Used:** Windows Command Prompt (CMD)

**Environment:** Windows with VMware network adapters

**Category:** Networking Fundamentals – Cybersecurity Practical

![ARP Table](Screenshots/ARP.1.png)

![IP Configuration](Screenshots/ARP.2.png)

![Filtered ARP Table](Screenshots/ARP.3.png)

![Ping Test](Screenshots/ARP.4.png)

![ARP Verification](Screenshots/ARP.5.png)
