# Day 8 — IPv4 Address Structure & Classes

## Key Concepts
An IPv4 address is four 8-bit numbers (octets) separated by dots, e.g.
192.168.1.10, totaling 32 bits. Addresses are historically grouped into
Classes A, B, and C based on the first octet's range, which determines
the default network size.

## Why It Matters
Recognizing a Class C address (192.168.x.x) instantly signals a small
home/office network, useful context when a user reads an IP over the phone.
An address starting with 169.254 is APIPA, meaning DHCP failed, not a
real network address.

## Interview Q&A
**Q: What class is 10.0.0.5, and how do you know?**
Class A — addresses with a first octet from 1-126 fall into Class A,
reserved for very large networks.

**Q: A user reads you 169.254.10.5. What does that tell you?**
That's an APIPA address, meaning the device failed to get an IP from
DHCP and self-assigned one. The real problem is a DHCP failure.
