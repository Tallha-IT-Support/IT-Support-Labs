# Day 12 — Week 2 Review — Diagnosing a "No Internet" Ticket With CLI Tools

## Key Concepts
Consolidation day combining ipconfig, ping, and nslookup into one real
triage workflow: ipconfig /all → ping gateway → ping 8.8.8.8 → nslookup
a domain, the exact sequence used on an actual support call.

## Why It Matters
This exact workflow is often asked verbatim in L1 helpdesk interviews as
a scenario question. Documenting each command's result (not just "checked,
it's fine") matters if the ticket gets escalated or reopened.

## Lab
Simulated a full "the internet isn't working" ticket: ran ipconfig /all,
pinged the gateway, pinged 8.8.8.8, then ran nslookup on a domain, recording
each result in order to isolate exactly where the problem would be.

## Interview Q&A
**Q: Walk me through your triage order for a "the internet isn't working" ticket.**
First ipconfig /all to check for a valid IP, then ping the gateway to
confirm local connectivity, then ping an external IP like 8.8.8.8 for WAN
reachability, then nslookup a domain to isolate DNS specifically.

**Q: Why document each command's result instead of writing "checked, it's fine"?**
A vague note doesn't hold up if escalated or reopened, specific results let
the next person pick up exactly where you left off.

<img width="568" height="515" alt="ping nslookup" src="https://github.com/user-attachments/assets/3e009e12-cdf2-4983-9873-92f828787111" />
