---
title:  "SampleHST summary & discussion"
layout: post
---

Research Question(s): 1) How can distributed traces be efficiently sampled on-the-fly in an unsupervised manner (to reduce the storage overhead of tracing)? 2) Can we design a sampling strategy that focuses on anomalous traces while also collecting normal traces?

Key Contributions: 1) The SampleHST Algorithm is an online clustering algorithm based on mass-based clustering. They use half-space trees (HSTs) to classify the traces (which is useful for anomaly detection). The HSTs are created by dividing the traces by trace attributes (e.g. trace has an error?). They create a forest of HSTs where different attributes are selected to divide traces. Given the HST forest, they calculate the mean mass score (percent of traces that had the same set of attributes) and 5th percentile mass score for each trace and cluster based on these two values. They show that these two mass-based properties are sufficient for clustering similar traces (when compared to the standard DBSCAN). They adjust sampling rates for cluster, proritizing clusters with anomalous traces. 2) They trade-off between sampling normal vs anomalous traces while remaining under a sampling budget. To do this, they only sample normal traces when the budget is higher than the percent of anomalous traces (which is calcuated using the HSTs). If the budget is lower than the percent of anomalous traces, they emphasize sampling anomalous traces over normal ones. 

Opportunities for future work: 1) This tool requires tail-based sampling meaning we must collect all instrumentation before deciding which traces we want to store. Tail-based sampling is not feasible in large scaled systems, so future work could be to explore ways to reduce the amount of instrumentation collected before making storage decisions. 2) Scalability- They encode each trace as a count vector, where the length of the vector is the number of unique spans (+ any additional attributes) seen across all traces. This value can be extremely large and dynamic. Additionally, a count vector cannot capture variations like order calls were made and latency information that could vary across traces with the same span counts. More accurate & flexible methods of encoding traces need to be explored to be useful in industrial systems. 

Presenter: Darby Huye

