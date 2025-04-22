# Chapter 1: Primer on Latency and Bandwidth

Speed is a feature - one of the most fundamental aspects of web performance.

## Understanding Latency and Bandwidth

**Latency** is the time it takes for a packet to travel from source to destination. The Hibernia Networks example demonstrates how companies invest millions in reducing latency even by milliseconds because it's that critical.

Latency comprises four components:

1. **Propagation delay**: Time for signal to travel through the medium
2. **Transmission delay**: Time to push bits onto the wire/medium
3. **Processing delay**: Time to process packet headers/routing
4. **Queuing delay**: Time spent waiting in buffer queues

**Bandwidth** measures how much data can be transferred per second (bps = bits per second, Bps = Bytes per second).

## The Last Mile Problem

This refers to the final leg between ISP and end user - typically where significant latency adds up due to older infrastructure and multiple network hops.

## Human Perception of Lag

300ms is the threshold where humans noticeably perceive delay. While we don't typically think in milliseconds, our sensitivity to lag is remarkably acute at this scale.

## Performance Reality Check

Contrary to common belief, latency—not bandwidth—is the primary performance bottleneck for most websites. Tools like traceroute help diagnose where latency accumulates along a route.

## Physics and Solutions

Light speed is fixed; we can't make data travel faster than physics allows. Instead, we:

- Minimize round trips
- Position data closer to clients (CDNs)
- Build applications that mask latency through caching, prefetching, and predictive loading

The fundamental insight: instead of fighting physics, work around it through smart architecture and application design.
