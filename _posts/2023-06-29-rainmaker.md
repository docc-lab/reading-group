---
title:  "Rainmaker summary & discussion"
layout: post
---

Cloud-based environments present error-handling challenges that vary significantly from those found in co-located application environments, where all errors can typically be handled by the same underlying programming frameworks. In cloud-based environments, causes of errors on one machine are opaque to other machines, and miscommunication of these errors can lead to widespread problems in cloud-backed applications. The authors of Rainmaker pose the question of whether it is possible to create a unified model for testing and identifying application failure scenarios in the face of mis-handled errors across components, and present a drop-in framework for automating testing of error mis-handling. By injecting HTTP errors and timeouts into cross-machine HTTP calls, Rainmaker is able to create failure scenarios which would otherwise be easy to miss due to the vast space of possible failures and interactions among different application components.


Presenter: Tomislav Zabcic-Matic

