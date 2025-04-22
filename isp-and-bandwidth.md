# Understanding ISP and the Bandwidth vs Latency Bottleneck

## What is an ISP?

ISP stands for Internet Service Provider. It's the company that connects you to the internet - think Comcast, AT&T, Verizon, or your local cable company. ISPs provide the infrastructure and network pathways that connect your home or business to the broader internet.

## Why Bandwidth Isn't the Bottleneck

This is a common misconception that's worth understanding deeply.

For most websites:

1. **Websites don't send that much data**  
   Most web pages are 1-5MB in size. Even at modest bandwidth speeds (10-20 Mbps), that's less than a second to transfer.

2. **The real delays are in round trips**  
   When you load a webpage, your browser makes multiple round trips to the server:

   - DNS lookup
   - TCP connection setup
   - TLS/SSL handshake
   - Initial HTML request
   - Subsequent CSS, JavaScript, image requests

   Each round trip incurs the full latency delay. With 100ms latency, a page requiring 10 round trips adds 1 second of delay just in waiting.

3. **Protocols have inherent delays**  
   TCP starts slow (congestion control) and requires acknowledgments before sending more data. These protocol behaviors create delays regardless of available bandwidth.

4. **Most bandwidth goes unused**  
   Many internet connections have ample bandwidth that remains underutilized during typical browsing. The bottleneck is waiting for responses, not transmitting data.

This is why CDNs and edge computing exist - they address latency by moving data closer to users, not by increasing bandwidth.
