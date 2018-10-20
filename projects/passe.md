---
layout: project
title: "Automating Application Security for Cloud Services"
project_id: passe
---

Network services play a central role in users’ online experiences. In doing so,
these services often gather significant amounts of valuable, user-specific, and
sometimes privacy-sensitive data. Unfortunately, in many client-facing
applications, a vulnerability in any part may compromise the entire
application. In order to address this problem, we have designed and implemented
Passe, a system that protects a data store from unintended data leaks and
unauthorized writes even in the face of application compromise.

Passe automatically splits (previously shared-memory-space) applications into
sandboxed processes. Passe limits communication between those components and
the types of accesses each component can make to shared storage, such as a
backend database. In order to limit components to their least privilege, Passe
uses dynamic analysis on developer-supplied end-to-end test cases to learn data
and control-flow relationships between database queries and previous query
results, and it then strongly enforces those relationships.

Our prototype of Passe acts as a drop-in replacement for the Django web
framework. By running eleven unmodified, off-the-shelf applications in Passe,
we demonstrate its ability to provide strong security guarantees — Passe
correctly enforced 96% of the applications’ policies — with little additional
overhead. Additionally, in the web-specific setting of the prototype, we also
mitigate the cross-component effects of cross-site scripting (XSS) attacks by
combining browser HTML5 sandboxing techniques with our automatic component
separation.