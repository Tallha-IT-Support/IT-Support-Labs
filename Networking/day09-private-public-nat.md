# Day 9 — Private vs Public IP Ranges & NAT Concept

## Key Concepts
Private IP ranges (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16) are reserved
for internal networks and never routed on the public internet. NAT (Network
Address Translation) on a router translates internal private addresses to
one public address so the network can reach the internet.

## Why It Matters
When a user's "my IP" from a website doesn't match their ipconfig output,
that's normal, one is private (internal), one is public (post-NAT),
not a bug. Explaining NAT in one sentence resolves the confusion instantly.

## Interview Q&A
**Q: Explain what NAT does in one sentence.**
NAT translates many private internal IP addresses into one shared public
IP address so an entire office can share a single internet connection.

**Q: Why does a user's "my IP" from a website not match their ipconfig output?**
ipconfig shows the private internal IP, while the website shows the public
IP after NAT translation on the router, two different addresses for two
different purposes.
