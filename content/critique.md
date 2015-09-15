+++
Description = "In which a gauntlet is thrown down."
Tags = ["enterprise", "cloud native"]
date = "2015-09-12T15:48:41-07:00"
title = "Critique"
draft = false
menu = "main"

+++
# A Critique of 12Factor

Embed a tweet here:
 "Of course, the concept of 12Factor ignores Security and Maintenance entirely."

 1. There is a compromise on the one repo = one app, which is why we support Procfile: that of the asynchronous worker. Logically, the worker (consumes the queue) and the dispatch (publishes to the queue) often *are* the same application, although they run in separate processes and perhaps separate containers. And they’re scaled differently.

 2. This doesn’t go far enough - the OS / rootFS itself should be vendored, and the relationship between the app and the runtime/app server should be abstracted and isolated. Enterprises do this already, by supporting only one or two OS images via “Golden Image” management. Platform does this better. Also, it’s easier to understand Factor 2 if you explain the “Design, Build, Deploy, Run” separation. Most DevOps folks leave off Design time, which makes it impossible to talk intelligently about Spring Boot (since it changes the Design-time vs Build-time separations).

 3. The separation should be “Config, Credentials, and Code”. Keeping Credentials in with other non-privileged config is endlessly problematic, especially in regulated environments where developers MUST NOT have access to prod credentials.

 4. Backing services is mostly correct, but in the microservices world, applications are often promoted to backing services. This factor should be updated to talk about service discovery and client-side load balancing. Also, the simple “connection string” doesn’t hold enough metadata, as the platform or networking team needs to understand both what ports are needed, and whether the protocol is secure on the wire.

 5. As mentioned, this should be an earlier factor so that factor 2 makes more sense. And it should include the Design (or Authoring) stage. Making that stage explicit allows Dev/Ops to identify when they’re violating this factor.

 6. While this factor acknowledges proctypes, it does this without explicitly clarifying the confusion from factor 1. Also, the use of blobstores as a data service that replaces the use of local filesystems for build-time assets should be called out as a best practice.

 7. When talking about promoting apps to data services (in reference to factor 4), an intro of circuit breakers is appropriate. Out of which will naturally fall some discussion of “monitoring ports” or “status streaming”, ala what hystrix provides. There is a category of monitoring which HAS to be internal to the app, since only the app itself understands what status would be appropriate to expose.

 8. This factor is poorly written. The key concept, that processes should be managed by a platform or OS and not by the app, is buried at the end and ought to be part of #7. Talking about proctypes should be in factor 1. And trying to invent the term “process formation” is hubris and wasted words.

 9. Well written and complete. Could use the term “Immutable Infrastructure” to convey the idea that running deployments should never be patched, but always disposed of.

 10. No comment at this time :)

 11. The idea that development occurs locally and not in a managed platform is a bad one. If an app is going to run with concurrency, it needs to be continuously tested that way. See http://pistoncloud.com/2013/10/termie-time-farm-boy/ and http://pistoncloud.com/2014/01/farmboy-part-1-example/ (a project I designed and funded) for more on why development should use a platform.

 12. This factor is poorly thought out and poorly implemented. I’m a big fan of a standardized admin API, running on a non-routed port, for these functions. The pathological case is a schema migration, and it’s probably walking people through why it takes *4* deploys to do this properly in a modern microservices app.

 13. Audit: Every 12 factor app should be designed with audit in mind. At the very least, it should be simple to find out:
    1. What version of each component is running, bound on what port
    1. When it was deployed and started

 14. Auth: Given that every app may be developed and deployed by many different developers, for many different purposes in many different environments, all functions should use standard HTTP VERBS and descriptive URLS (whether they’re a REST API or not). It’s the responsibility of the runtime execution environment to provide AUTHN/AUTHZ integration on those URLS and VERBS - so that the various microservices will share RBAC appropriately.

 15. API first. I truly think this should be part of 12 factor. http://www.api-first.com/
