# Lab 04 – HTTP vs HTTPS Traffic Analysis

## Objective
To capture and analyse HTTP and HTTPS network traffic using Wireshark, understand how HTTP requests appear in packet captures, and observe how TLS encryption protects HTTPS communication.

## Tools & Technologies
- Wireshark
- Web browser
- NeverSSL – `http://neverssl.com`
- Example – `https://example.com`

---

## Part 1: HTTP Traffic Analysis

### Procedure

1. Started a packet capture in Wireshark.
2. Visited `http://neverssl.com` in the browser to generate HTTP traffic.
3. Stopped the capture after the webpage loaded.
4. Applied the following display filter:

   ```text
   http
   ```

5. When no packets appeared, used:

   ```text
   tcp.port == 80
   ```

6. Started a fresh capture and generated HTTP traffic again.
7. Applied:

   ```text
   tcp.port == 80 && tcp.len > 0
   ```

8. Inspected the packet details and located the **Hypertext Transfer Protocol** section.

### Observations

- Successfully captured HTTP traffic.
- Identified the Hypertext Transfer Protocol section in packet details.
- Inspected HTTP request fields, including the Request Method and Host.
- Observed TCP packets carrying application data.
- HTTP communication is not encrypted by default, meaning request contents may be readable in a packet capture.

---

## Part 2: HTTPS Traffic Analysis

### Procedure

1. Started a fresh packet capture in Wireshark.
2. Visited `https://example.com` to generate HTTPS traffic.
3. Stopped the capture after the webpage loaded.
4. Applied the
