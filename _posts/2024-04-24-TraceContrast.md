---
title: "Trace-based Multi-Dimensional Root Cause Localization of Performance Issues in Microservice Systems"
layout: post
---

Research Question: Can we identify root causes of performance problems by analyzing differences in the critical paths of normal and anomalous requests?

Key Contributions: This paper presents TraceContrast, a framework for analyzing the critical paths of request traces from distributed systems, finding disparities between the patterns within anomalous traces and normal traces, and using that information to localize causes of performance problems within these workflows. In particular, the approach presented in this paper notes that performance problems may arise not just due to a single component's functionality but can often arise due to the interplay between various components, and this the approach aims to identify sequential patterns that indicate poor performance.

By representing critical paths as sequences of events, the paper's approach is able to group paths into sequences of identical structure, and then combine those sequences into prefix trees, where divergences in the sequences cause branching. These sequences include not only tracepoint IDs but also include information such as version information and key-value data. By identifying nodes in the prefix trees that correspond to a high prevalence of anomalous traces versus normal traces, the algorithm is able to identify relevant trace sequences that point towards anomalous behavior. The algorithm outputs a ranked set of features meant to capture the root cause of a performance problem.

Opportunities for future work: The approach presented in this paper focuses exclusively on critical paths of requests suffering from performance problems. However, this method appears to be extendable in order to compare broader workflow patterns and to identify workflow properties at large that may contribute to performance problems in a system, particularly for non-problematic requests whose execution can be causally related to the execution of problematic requests.

Presenter: Tomislav Zabcic-Matic