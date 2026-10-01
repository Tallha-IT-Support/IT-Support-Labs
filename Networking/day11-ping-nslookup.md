# Day 11 — ping, nslookup & Basic Connectivity Testing

## Key Concepts
ping tests basic reachability by sending packets and timing the reply.
nslookup queries DNS to show what IP a domain name resolves to. Together
they're the fastest way to tell if a problem is connectivity or DNS.

## Why It Matters
"Ping the gateway, ping 8.8.8.8, then nslookup a website" is the standard
3-step triage used in the first 60 seconds of a "no internet" call.

## Lab
Ran `ping 127.0.0.1` (loopback), then pinged the default gateway, then
`ping 8.8.8.8`, confirming each layer of connectivity in order. Ran
`nslookup google.com` and noted the IP it returned.

## Interview Q&A
**Q: What's the first command you'd run on a "no internet" call, and why?**
ping 127.0.0.1 first to confirm the network stack itself works, then the
default gateway, before testing anything external, isolating the problem fastest.

**Q: Ping to 8.8.8.8 works but nslookup fails. What's the problem?**
That's a DNS-specific problem, not connectivity. The network path works,
but name resolution is broken. I'd try a different DNS server like 1.1.1.1.

<img width="568" height="515" alt="ping nslookup" src="https://github.com/user-attachments/assets/4221357b-5d3d-491d-a038-2675a819dbee" />
