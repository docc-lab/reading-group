---
title:  "A Cloud-Scale Characterization of Remote Procedure Calls"
layout: post
---


Research Question(s): RPC is a key enabler for cloud-scale distributed applications and its use increases rapidly. Characterizing RPCs usage in the cloud helps with better understanding of cloud applications, yielding insights for optimizations. This paper presents methodology and results of characterizing RPCs at Google.


Key Contributions: By analyzing monitoring datasets of metrics, traces, and CPU cycles spent on processing RPCs, the authors show that 1) the characters of latency, frequency, size, and nested hierarchy of over 10,000 distinct RPC methods and find that on average RPCs at Google operate at millisecond timescale (not microseconds which was the focus in many prior work) and kilobyte sizes. The RPC traces are wider than deeper, which is consistent with prior work; 2) At the tail, RPC latency tax, which is defined as non-application latencies, dominates a request's latency, indicating the importance of optimization of RPC; 3) They further breakdown the RPC latency tax into nine components and study latency variations within and across clusters, concluding that high server and memory utilization correlates with high variation within clusters. 4) Lastly, they find that RPC CPU utilization is heavily tailed. Also, most CPU cycles are consumed by a few services. Both results reveal the need for method-specific hardware optimization.


Opportunities for future work: This work studies RPCs sent over TCP, leaving it a future work to study RPCs over RDMA, an important alternative transport. Also, inherently, the results hold at Google, but unclear if other cloud providers have similar concerns.


Presenter: Max Liu
