# Day 5 — OSI Model — Layers 4-7

## Key Concepts
- Layer 4 (Transport): TCP (reliable) vs UDP (fast), port numbers, firewall filtering
- Layers 5-6 (Session/Presentation): connection handling, encryption (TLS/SSL)
- Layer 7 (Application): what the user actually sees — browser, email client

## Why It Matters
"Ping works but the site won't load" usually means a blocked port (L4) or the
app itself being down (L7) — ping succeeding rules out L1-L3.

## Interview Q&A
**Q: What's the difference between TCP and UDP?**
TCP guarantees delivery and order (web pages); UDP is faster with no guarantee
(video calls, live streaming), where speed matters more than perfection.
