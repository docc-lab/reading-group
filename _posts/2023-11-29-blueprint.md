---
title:  "Blueprint: A Toolchain for Highly-Reconfigurable Microservices"
layout: post
---

Research Question(s): How to easily reconfigure microservice
applications for 1) update microservices design, 2) reproduce emergent
phenomena in microservices and
3) prototype and evaluate solutions for microservices.

Key Contributions: Hard to explore and standardize is the design space
of microservice systems, yet point solutions in such a vast design
space are the norm in microservice benchmarks. Hence, the
generalizability of research results derived from such benchmarks is
questionable. Additionally, microservice implementations tightly
couple concerns at source-code level, so a slight alteration of design
requires a lot of efforts (hundreds to thousands of lines of code). 

Blueprint’s key insight is that the design of a microservice
application can be decoupled into three almost independent layers  (i)
the application level workflow that defines APIs used by
microservices, (ii) the underlying scaffolding components such as
replication and auto-scaling frameworks, communication libraries, and
storage backends , and (iii) the concrete instantiations of those
components and their configuration. Using this insight, Blueprint
compiler first takes three inputs, workflow spec, wiring spec, and
compiler plugins, and generates an intermediate representation(IR). An
IR is a structured graph specifying the services, and scaffolding
(e.g. distributed tracing), and instantiation granularity (e.g. Linux
Process and Docker Container). The compiler then uses the IR to
generate runnable microservice applications. Using Blueprint, a
researcher can change the design of a microservice by simply updating
one or more of workflow spec, wiring spec and compiler plugins. 

Blueprint is able to reduce the number of lines of code for
implementing a microservice benchmark by 5-7X. The lines of code
required for changing a design choice has 17X reduction. Blueprint can
reproduce emergent phenomena like metastable failures and cross-system
inconsistency by 3-4 lines of code in the wiring spec. Blueprint can
generate runnable small to medium sized microservice applications
within seconds (1-3 sec). 


Opportunities for future work:  1) Debugging generated code and
runnable systems can be challenging. 2) Currently, Blueprint generates
services only in Go. More compiler plug-ins in the future may support
other programming languages. 3) The abstractions Blueprint are great
for reconfiguring applications, but at the cost of potentially
performance optimizations. This performance tax may make Blueprint not
suitable for generating production-ready microservice applications. 


Presenter: Max Liu

