---
title:  "Understanding host network stack overheads"
layout: post
---

For this week, we cover [Understanding host network stack overheads](https://dl.acm.org/doi/abs/10.1145/3452296.3472888).

**Research Question:**

1. What are the performance bottlenecks in the host network stack?
2. What is the impact of various factors or tenchniques on network stack performance? Specificly, they covered number of flows, in-network congestion, Data-Direct I/O (DDIO), Input/Output Memory Management Unit(IOMMU), different workload patterns.
3. What are the implications of the findings on designing future operating systems, network protocols, and network hardware?

**Key Contributions:**

The contributions of this paper include studying the performance of host network stacks in the context of increasing datacenter access link bandwidths and limited host resources. The paper explores various solutions such as Linux network stack optimizations, hardware offloads, RDMA, clean-slate userspace network stacks, and specialized host network hardware. The paper also investigates the impact of in-network congestion, the use of DDIO, and the implications of reducing the gap between bandwidth-delay product and cache sizes. Additionally, the paper discusses the potential benefits of emerging zero-copy mechanisms and hardware offloads for improving CPU efficiency in network stacks.

This is not an orthodox system paper but kinda like detective fiction on network stack performance. The whole network stack is not something distributed tracing capable of instrumenting without sophsicated effort (like Theon's Foxhound), but we still are be able to extend application layer observability into relative lower parts in network stack. This paper provides a excellent guide of where and what to dive deeper.

Presenter: Zhaoqi(Roy) Zhang
