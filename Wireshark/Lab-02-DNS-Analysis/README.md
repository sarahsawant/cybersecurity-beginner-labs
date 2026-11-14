# Wireshark Lab 02 – DNS Traffic Analysis

## Aim
To capture and analyze DNS traffic using Wireshark and understand how domain names are translated into IP addresses.

## Tools Used
- Wireshark
- Windows Command Prompt
- nslookup

## Commands Used
```cmd
nslookup example.com
```

## Procedure
1. Opened Wireshark and started packet capture on the active network interface.
2. Executed `nslookup example.com` in Command Prompt.
3. Applied the display filter `dns` in Wireshark.
4. Identified DNS Standard Query packets.
5. Inspected DNS query details, including domain name, record type and class.
6. Examined IP addresses and UDP port information in the captured traffic.
7. Stopped the capture and saved it in PCAPNG format.

## Observations
- Domain queried: `example.com`
- DNS record types observed: A and AAAA
- DNS class: IN
- DNS server/router address observed: `192.168.0.1`
- Another local device address observed: `192.168.0.103`
- UDP source port observed in a response-direction packet: 53
- UDP destination port observed: 58280

## Key Learnings
- DNS translates domain names into IP addresses.
- A records are used for IPv4 addresses.
- AAAA records are used for IPv6 addresses.
- DNS commonly uses UDP port 53.
- Client devices use temporary source or destination ports for DNS communication.

## Capture File
`Lab-02-DNS-Analysis.pcapng`

## Conclusion
Successfully captured and inspected DNS traffic using Wireshark. Identified DNS queries, record types, local IP addresses and UDP port information.
