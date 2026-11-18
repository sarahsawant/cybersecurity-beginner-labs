## TryHackMe Room

[DNS in Detail – Completed](https://tryhackme.com/room/dnsindetail)
# TryHackMe – DNS in Detail

**Platform:** TryHackMe  
**Category:** Networking Fundamentals  
**Status:** Completed  
**Date:** 18 November 2026

[Open TryHackMe Room – DNS in Detail](https://tryhackme.com/room/dnsindetail)

---

## 1. Objective

To understand the Domain Name System (DNS), how domain names are resolved into IP addresses, and how different DNS record types are used in network communication.

## 2. Concepts Learned

### DNS (Domain Name System)

DNS translates human-readable domain names into IP addresses so that computers can communicate with servers over a network.

For example, DNS helps translate `google.com` into its corresponding IP address.

### DNS Record Types

| Record | Description |
|---|---|
| A | Maps a domain name to an IPv4 address |
| AAAA | Maps a domain name to an IPv6 address |
| CNAME | Points an alias to another domain name |
| MX | Specifies the mail servers responsible for receiving emails |
| TXT | Stores text-based information associated with a domain |
| NS | Identifies the authoritative name servers for a domain |
| PTR | Maps an IP address back to a domain name |

### Other Important Concepts

- **TTL (Time To Live):** Specifies how long a DNS record can remain cached.
- **Authoritative DNS Server:** Holds the official DNS records for a domain.
- **MX Priority:** Determines the preference of mail servers. A lower numerical value indicates higher priority.
- **DNS Resolution:** The process of finding the IP address associated with a domain name.

## 3. Practical Implementation

Practised DNS record investigation using Windows Command Prompt and the `nslookup` utility.

### Commands Used

**A Record Lookup**
```cmd
C:\Windows\System32\nslookup.exe -type=A www.website.thm
```

**CNAME Record Lookup**
```cmd
C:\Windows\System32\nslookup.exe -type=CNAME shop.website.thm
```

**MX Record Lookup**
```cmd
C:\Windows\System32\nslookup.exe -type=MX website.thm
```

**TXT Record Lookup**
```cmd
C:\Windows\System32\nslookup.exe -type=TXT website.thm
```

**Reverse DNS Lookup**
```cmd
C:\Windows\System32\nslookup.exe 8.8.8.8
```

## 4. Key Takeaways

- DNS plays an important role in connecting domain names with network addresses.
- Different DNS record types serve different purposes.
- TTL helps control DNS caching.
- Authoritative DNS servers provide official domain records.
- Reverse DNS helps identify domain names associated with IP addresses.
- `nslookup` is useful for DNS troubleshooting and investigation.

## 5. Industry Relevance

Understanding DNS is important in cybersecurity because DNS investigation can help with:

- Network troubleshooting.
- Network reconnaissance.
- Domain and infrastructure investigation.
- Identifying suspicious DNS records.
- Investigating potential DNS-based attacks.

## 6. Skills Practised

- DNS fundamentals.
- DNS record identification.
- Windows Command Prompt.
- `nslookup` utility.
- Forward and reverse DNS lookups.
- Basic network investigation.

## 7. Completion

Successfully completed the TryHackMe **DNS in Detail** room and practised identifying different DNS record types.

**Next Learning Objective:** DNS Spoofing and DNS Cache Poisoning.
