# Day 14 — The Subnetting Formula

## Key Concepts
Usable hosts per subnet = 2^h - 2, where h is the number of host bits.
The "-2" accounts for the network address (all host bits 0) and the
broadcast address (all host bits 1), neither of which can be assigned
to a device. Each extra network bit borrowed halves the usable hosts.

## Lab
Split 192.168.1.0/24 into two /26 subnets (255.255.255.192), each with
6 host bits → 2^6 - 2 = 62 usable hosts per subnet:
- Subnet 1: 192.168.1.0/26 — router Fa0/0: .1, PC0: .2
- Subnet 2: 192.168.1.64/26 — router Fa0/1: .65, PC1: .66

Verified the formula directly in Packet Tracer by attempting to assign
the network address (.0, .64) and broadcast address (.63, .127) to a PC,
both rejected as "Invalid IP" as predicted. Confirmed routing between the
two subnets with a successful ping from PC0 to PC1 across the router.

## Troubleshooting
- Got an "overlaps with FastEthernet0/0" error when configuring Fa0/1,
  caused by Fa0/0 still using the old /24 mask, which claimed the entire
  .0–.255 range. Fixed by shrinking Fa0/0 to /26 first.
- A ping that kept timing out traced back to being in `Router>` (user
  EXEC mode) instead of `Router#`, so `show running-config` and other
  privileged commands were silently unavailable.

## Interview Q&A
**Q: How many usable hosts are in a /26 subnet, and how do you get that number?**
62. A /26 leaves 6 host bits, so 2^6 = 64 total addresses, minus 2
(network and broadcast) = 62 usable.

**Q: Why would two directly-connected router interfaces fail with an "overlaps" error?**
Because their subnet masks still overlap in address range, two interfaces
can't claim addresses from the same subnet range at once, each needs its
own distinct subnet.


<img width="1872" height="1946" alt="b6e514af-e179-4dc8-a2fb-4bc2c217a819" src="https://github.com/user-attachments/assets/6b57d4e1-ca90-440c-a5c5-e30afffddb01" />
