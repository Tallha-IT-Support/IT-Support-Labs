# Day 10 — ipconfig / ifconfig — Reading Your Own Network Config

## Key Concepts
ipconfig (Windows) and ifconfig/ip addr (Linux) display a device's current
network configuration: IP address, subnet mask, default gateway, and DNS
servers. ipconfig /all shows extended detail including MAC address and
DHCP lease info.

## Why It Matters
This is the single most-used command in L1 support, nearly every "no
internet" ticket starts with running ipconfig /all. A 169.254.x.x address
means DHCP failed, fixed by ipconfig /release then ipconfig /renew.

## Lab
Ran `ipconfig /all` on my own PC and identified: IP address, subnet mask,
default gateway, DNS servers, and MAC address.

## Interview Q&A
**Q: What's the difference between ipconfig and ipconfig /all?**
ipconfig shows a quick summary (IP, mask, gateway). ipconfig /all shows
the full picture including MAC address, DHCP server, and lease times.

**Q: What would you do if ipconfig shows a 169.254.x.x address?**
That indicates DHCP failed. I'd run ipconfig /release then ipconfig /renew,
then check the physical connection if that doesn't resolve it.

<img width="830" height="768" alt="ipconfigall_blurred" src="https://github.com/user-attachments/assets/51014cb2-258f-478e-bfe2-232c5051151f" />
