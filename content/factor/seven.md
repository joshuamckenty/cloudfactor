+++
Categories = ["Development", "GoLang"]
Description = ""
Tags = ["Development", "golang"]
date = "2015-09-17T14:54:13+10:00"
# menu = "main"
title = "Service Binding (was: Port Binding)"

+++

 When talking about promoting apps to data services (in reference to factor 4), an intro of circuit breakers is appropriate. Out of which will naturally fall some discussion of “monitoring ports” or “status streaming”, ala what hystrix provides. There is a category of monitoring which HAS to be internal to the app, since only the app itself understands what status would be appropriate to expose.
