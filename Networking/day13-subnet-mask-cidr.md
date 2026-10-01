# Day 13 — What Is a Subnet Mask & CIDR Notation

## Key Concepts
A subnet mask defines where the network portion of an IP address ends and
the host portion begins. CIDR notation (e.g. /24) is shorthand for how many
bits are used for the network part, 255.255.255.0 and /24 mean the same thing.

## Lab
Built a router + PC topology in Cisco Packet Tracer. Configured the router's
Fa0/0 interface with IP 192.168.1.1/255.255.255.0, and the PC with
192.168.1.10/255.255.255.0, gateway 192.168.1.1. Confirmed connectivity
with a successful ping from the PC to the router.

## Troubleshooting
- Accidentally ran `erase startup-config` + `reload`, which dropped the
  router into the setup wizard, fixed with Ctrl+C to exit it.
- Typo'd `fastEthrnet` instead of `fastEthernet`, causing "Invalid input" errors.
- Interface kept showing "administratively down": root cause was running
  `configure terminal` from `Router>` (user EXEC mode) instead of `Router#`
  (privileged EXEC mode). Fixed by running `enable` first.
- Diagnosed Layer 1 vs Layer 3 status using `show ip interface brief`,
  where Status "up" / Protocol "down" pointed to a physical link issue.

## Interview Q&A
**Q: What does /24 mean in an IP address like 192.168.1.0/24?**
It means the first 24 bits are the network portion, equivalent to a subnet
mask of 255.255.255.0, leaving 8 bits for host addresses.

**Q: An interface won't come up even though it's cabled and configured correctly. What's a non-obvious cause?**
Being in the wrong EXEC mode, if commands were entered from user EXEC mode
(Router>) instead of privileged EXEC mode (Router#), configuration changes
may not actually apply, even though no error is obviously thrown.

<img width="3072" height="4096" alt="2b43fde0-4d86-4569-9e7f-f4d88aa145f8" src="https://github.com/user-attachments/assets/74de55a0-51ed-4eb8-a375-646f6b3aa1e9" />


