---
title:  "Pivot Tracing summary & discussion"
layout: post
---

Research Question(s): How to correlate and group events across distributed components? How to avoid expensive data colletion during execution?

Key Contributions: 1) Introduced the "happened-before join" operator to group and filter events that causally precede each other in an execution, optimizing metric collections with the baggage abstraction. 2) Developed a prototype for Java-based systems and evaluated it on a heterogeneous Hadoop cluster, including HDFS, HBase, MapReduce, and YARN. 3) Achieved low execution overhead.

Opportunities for future work: 1) Their current definition of causality does not capture all possible causal relationships, including when events in the processing of one request could influence another. Our work can extend beyond a simple happened before relationship. 2) The propagation overhead is potentially unbounded (the number of packed tuples in a baggage can become enormous, although unlikely). In scenarios of excessive overhead, the system could switch to counting the number of tuples, but important information might still be missing when troubleshooting the root cause. More sampling strategies can be investigated to evaluate its scalability.

Presenter: Mona Ma