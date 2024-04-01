---
title:  "LatenSeer summary & discussion"
layout: post
---

Research Question(s):  Current methods for estimating latency in complex distributed systems are unrealistic. Challenges include handling diverse and complex traces (using set nodes), dealing with clock skews and path-dependent executions that make aggregated casual relationships hard to identify (using succession time), considering mutual independence (using joint latency profiling).

Key Contributions: Developed an offline tool for conducting latency estimation from distributed traces. 2) Improved data structures to accurately represent causal relationships and model latency at scale. 3) Achieved easy deployment, enabling the framework to integrate with existing data collection systems, built on top of Jeager & OTel; suitable to versatile scenarios where the system estimates end-to-end latency given hypothetical latency changes in any of its constituent services; and provides realistic forecasts.

Opportunities for future work: 1) Latency for span A is described by the equation L(𝐴) = L(𝐵) + L(𝐸) + L(𝐺) + L(N), where the child services 𝐵, 𝐸, and 𝐺 are on the latency-critical path and L(N) accounts for the network latency or other processing time. However, the internal dependencies of 𝐵, 𝐸, and 𝐺 might not be accurately reflected in the actual traces, as they could overlap in time or run concurrently. 2) Synchronization points for nodes may be imprecise, and assumptions about serial and parallel processing are based solely on succession time. Our work can validate the accuracy of the generated invocation graph.

Presenter: Mona Ma