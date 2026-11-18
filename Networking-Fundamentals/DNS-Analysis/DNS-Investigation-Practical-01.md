# DNS Investigation Using NSLOOKUP – Practical 01

## 1. Objective

To understand how DNS works and investigate DNS records using the Windows NSLOOKUP command-line utility.

This practical covers:
- Resolving domain names into IP addresses.
- Querying DNS using a specific DNS server.
- Identifying authoritative nameservers.
- Investigating mail exchange records.
- Examining TXT records.
- Understanding DNS responses.

## 2. Environment and Tools

- **Operating System:** Windows
- **Tool:** NSLOOKUP
- **Executable Path:** `C:\Windows\System32\nslookup.exe`
- **DNS Resolver:** `10.225.171.91`
- **Public DNS Resolver:** Google DNS (`8.8.8.8`)

## 3. Practical Exercises

### Exercise 1: Basic DNS Lookup (A and AAAA Records)

**Command:**
```cmd
C:\Windows\System32\nslookup.exe youtube.com
```

**Purpose:**

Resolve a domain name and retrieve its associated IP addresses.

**Observations:**
- The query returned multiple IP addresses.
- IPv4 addresses were returned as A records.
- IPv6 addresses were returned as AAAA records.
- The response was labelled Non-authoritative.

**Learning:**

A domain can have multiple IP addresses. DNS allows clients to resolve domain names into IP addresses so they can connect to the appropriate servers.

A non-authoritative response means the answer came from a DNS resolver rather than directly from the domain's authoritative nameserver.

### Exercise 2: Querying a Specific DNS Server

**Command:**
```cmd
C:\Windows\System32\nslookup.exe google.com 8.8.8.8
```

**Purpose:**

Resolve a domain using Google's public DNS resolver instead of the system's default DNS server.

**Observations:**
- DNS server: `dns.google`
- DNS server IP: `8.8.8.8`
- Multiple IPv4 and IPv6 addresses were returned.

**Learning:**

The second argument specifies which DNS server should process the query.

This helps compare DNS responses from different resolvers and troubleshoot DNS resolution issues.

### Exercise 3: Identifying Nameservers (NS Records)

**Command:**
```cmd
C:\Windows\System32\nslookup.exe -type=NS google.com
```

**Purpose:**

Identify the nameservers responsible for a domain.

**Observations:**

The query returned four nameservers:

- `ns1.google.com`
- `ns2.google.com`
- `ns3.google.com`
- `ns4.google.com`

**Learning:**

NS records identify the authoritative nameservers for a domain. These servers hold the DNS information used to answer queries about that domain.

### Exercise 4: Investigating Mail Exchange Records (MX)

**Command:**
```cmd
C:\Windows\System32\nslookup.exe -type=MX google.com
```

**Purpose:**

Identify the mail server responsible for receiving email for a domain.

**Observation:**

The query returned:

- Mail exchanger: `smtp.google.com`
- Preference: `10`

**Learning:**

MX records specify which mail servers receive email for a domain.

The preference value determines priority when multiple mail servers are configured. A lower preference value indicates higher priority.

### Exercise 5: Investigating TXT Records

**Command:**
```cmd
C:\Windows\System32\nslookup.exe -type=TXT google.com
```

**Purpose:**

Retrieve TXT records associated with a domain.

**Observations:**

The query returned several TXT records, including:
- Domain verification records.
- Third-party service verification strings.
- Email authentication information.

One important record observed was:

```text
v=spf1 include:_spf.google.com ~all
```

**Learning:**

TXT records store text-based information associated with a domain.

They are commonly used for:
- Domain ownership verification.
- Email authentication.
- SPF (Sender Policy Framework).
- Security-related configuration.

The SPF record specifies which sending sources are authorized under the domain's SPF policy. The `~all` mechanism indicates a soft-fail for sources that do not match the policy.

## 4. Additional Verification

Verified the location of the NSLOOKUP executable using:

```cmd
dir C:\Windows\System32\nslookup.exe
```

The file was successfully located in the Windows System32 directory.

## 5. Key Concepts Learned

| DNS Record | Purpose |
|---|---|
| A | Maps a domain to an IPv4 address |
| AAAA | Maps a domain to an IPv6 address |
| NS | Identifies authoritative nameservers |
| MX | Identifies mail servers |
| TXT | Stores text-based DNS information |
| PTR | Maps an IP address to a hostname |

## 6. Cybersecurity Relevance

DNS investigation is useful in cybersecurity for:

- Network reconnaissance.
- Domain and infrastructure analysis.
- Identifying mail infrastructure.
- Examining email authentication configurations.
- Troubleshooting DNS-related issues.
- Supporting investigations into suspicious domains.

DNS enumeration is an important preliminary skill in network security assessments.

## 7. Practical Status

**Completed:** Basic DNS investigation using NSLOOKUP.

**Environment:** Windows Command Prompt.

**Next learning objective:** Reverse DNS lookup using PTR records and further DNS investigation.

---

*This practical was performed in a local Windows environment using publicly available DNS information.*
