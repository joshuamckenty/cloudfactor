+++
Categories = ["Development", "GoLang"]
Description = ""
Tags = ["Development", "golang"]
date = "2015-09-17T14:54:31+10:00"
# menu = "main"
title = "Operational Tasks (was: Admin Processes)"

+++

This factor is poorly thought out and usually poorly implemented.

I’m a big fan of a standardized admin API, running on a non-routed port, for these functions. The pathological case is a schema migration, and it’s probably worth walking people through why it takes _4_ deploys to do this properly in a modern microservices app.
