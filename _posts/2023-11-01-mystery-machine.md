---
title:  "The Mystery Machine summary & discussion"
layout: post
---

Research Question(s): How to conduct performance analysis on complex, large-scale, heterogeneous distributed systems? How to construct causal relationships between components? How to obtain the true dependency? 

Key Contributions: 1) The authors built a causal model without extensive instrumentation but used a large number of already-existing log messages. 2) They leveraged the large sample size and natural variation in ordering of different observed request traces to infer causal dependencies between components. 3) They applied the strategy of eliminating contradictions to the domain of distributed tracing. 4) They verified that individual components can be well-optimized in isolation, where performance improvements usually involve the interaction of multiple components.

Opportunities for future work: 1) The Happens-before relationship type introduced unnessasery complexities to their dependency model. Dependency edges between parallel workloads can be discarded since they only represent temporal orders instead of any significant casual relationships. 2) They defined critical path to be "the set of segments for which a differential increase in segment execution time would result in the same differential increase in end-to-end latency" and performed longest-path analysis from the first service to the end, whereas recent papers defined critical path algorithm to walk backward and pick the least returned service. It would be interested to look into how different critical path algorithms contributed to the accuracy of identifying the longest series of sequential operations in a parallel computation system.

Presenter: Mona Ma

