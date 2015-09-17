+++
date = 2015-09-12T23:33:29Z
draft = false
title = "About"
# menu = "main"

+++

The notion of the [12factor application](http://12factor.net), while revolutionary,
has unfortunately led an entire generation of software developers off the path and
deep into the woods.

It is predicated on the concept of a "runtime environment", or platform, where such
cloud native applications can be hosted. Yet all discussion of the qualifications
of such a platform was left out of the manifesto.

We aim to fix this.

# A Critique of 12 Factor

[Factor One: One Application, One Repository](/factor/one)

[Factor Two: Dependencies: Vendored and Explicit](/factor/two)

[Factor Three: Divide and Conquer](/factor/three)

[Factor Four: Backing Services](/factor/four)

[Factor Five: Pipeline Stages](/factor/five)

[Factor Six: Stateless](/factor/six)

[Factor Seven: Service Binding](/factor/seven)

[Factor Eight: Process Management](/factor/eight)

[Factor Nine: Immutable Infrastructure](/factor/nine)

Factor 10. No comment at this time :)

[Factor Eleven: Logs](/factor/eleven)

[Factor Twelve: Operational Tasks](/factor/twelve)

## A few more factors...

  #13. Audit: Every 12 factor app should be designed with audit in mind. At the very least, it should be simple to find out:
    1. What version of each component is running, bound on what port
    1. When it was deployed and started

  #14. Auth: Given that every app may be developed and deployed by many different developers, for many different purposes in many different environments, all functions should use standard HTTP VERBS and descriptive URLS (whether they’re a REST API or not). It’s the responsibility of the runtime execution environment to provide AUTHN/AUTHZ integration on those URLS and VERBS - so that the various microservices will share RBAC appropriately.

  #15. API first. I truly think this should be part of 12 factor. http://www.api-first.com/
