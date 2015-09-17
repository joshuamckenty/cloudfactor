+++
Categories = ["Development", "GoLang"]
Description = ""
Tags = ["Development", "golang"]
date = "2015-09-17T13:22:00+10:00"
# menu = "main"
title = "Dependencies: Vendored and Explicit"

+++

 This doesn’t go far enough - the OS / rootFS itself should be vendored, and the relationship between the app and the runtime/app server should be abstracted and isolated. Enterprises do this already, by supporting only one or two OS images via “Golden Image” management. Platform does this better. Also, it’s easier to understand Factor 2 if you explain the “Design, Build, Deploy, Run” separation first. Most DevOps folks leave off Design time, which makes it impossible to talk intelligently about Spring Boot (since it changes the Design-time vs Build-time separations).
