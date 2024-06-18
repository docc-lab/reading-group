---
title: "Autothrottle: A Practical Bi-Level Approach to Resource Management for SLO-Targeted Microservices"
layout: post
---


Research Question: How can current auto-scaling approaches be improved for microservice applications, in order to minimize cost and SLO violations in the face of dynamically changing workloads?

Key Contributions: The authors present Autothrottle, a "bi-level learning assisted framework" for automatically adjusting resource allocations dynamically per microservice instance.  Autothrottle employs a global, application-wide component (Tower) and a per-microservice component (Captains).  Tower uses an online learning approach (contextual bandits) to set throttle targets for clustered classes of microservice; these targets are periodically (per-minute) sent to the Captains, which monitor the number of CPU throttling events for their service and adjust the service's cgroup quota to try to hit the target throttling rate.  Captains are biased to react very quickly to a throttle rate above target by increasing CPU quota in order to avoid SLO violation.  The use of CPU throttling events as a proxy metric for request latency was chosen because it was found empirically to have better correlation than the more typically used CPU utilitization (5.3, Figure 7).  Another interesting design choice is to use k-means clustering to group microservices by average CPU utilization, and then set throttle targets per group.  It was found that the best choice for k is 2, after which returns diminish (5.3 "Number of Performance Targets").  Autothrottle was able to consistently outperform the K8s CPU and CPU-Fast autoscalers and Sinan (a state-of-the-art ML based autoscaler), with 25%-50% lower resource allocation to satisfy the SLO.  Interestingly, it does this while maintaining a worse (higher) P99 latency (while still under SLO), indicating a much lower variance and more stable performance (5.4, Figure 9b).

The k=2 clustering approach seems to suggest the microservices in the benchmark applications (Social-Network, Train-Ticket, and Hotel-Reservation) sort roughly into CPU-intensive and non-CPU-intensive, and further that this classification strongly predicts how sensitive the end-to-end application latency is to rate of CPU throttling within each group.

Opportunities for future work: 

1. Applying the approach to different resource types like memory and storage
2. Adding horizontal scaling (in addition to vertical-scaling) to the action model

Presenter: Tony Astolfi
