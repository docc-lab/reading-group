---
title: "Understanding and Detecting Software Upgrade Failures in Distributed Systems"
layout: post
---

Research Question(s): How can we effectively detect software upgrade failures in distributed systems? How can we most effectively diagnose the causes of version compatibility issues that cause upgrade failures?

Key Contributions: This paper presents a framework for both detecting and diagnosing the causes of upgrade-related failures in distributed systems. It presents DUPTester, a version compatibility testing tool that systematically tests for problems between different software versions, and DUPChecker, a tool for discovering incompatibilities between the data formats used and required by different versions of the same software. The paper presents two key insights regarding upgrade failures - the first being that most upgrade failures can be detected by testing between at most 2 version upgrades, and the second being that most failures can be detected by running workloads already present in the provided test suites. Through a thorough study of upgrade failures, the authors identify that two major categories of upgrade failure causes are incompatibilities between versions and broken upgrade operations, and identify several major categories of incompatibilities - namely, incompatibilities in data syntax (in serialization libraries) and data semantics.

The work finds that typically only three nodes are needed to replicate most kinds of failures, and the diagnostic system presented in the work uses 3-node configurations in order to test combinations of versions that are up to two versions apart, in line with the findings from the study of upgrade failures. Additionally, the work presents a static analysis tool that is able to identify incongruities between the data syntax and semantics of different software versions.

Opportunities for future work: One possible avenue for future work would be to look into the integration of a system for detecting and diagnosing upgrade failures into a broader problem diagnosis system in order to assist in the identification of root causes of both correctness and performance problems in distributed systems.

Presenter: Tomislav Zabcic-Matic