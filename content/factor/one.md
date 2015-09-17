+++
Categories = ["Development", "GoLang"]
Description = "One Repo, One Application"
Tags = ["Development", "golang"]
date = "2015-09-17T13:16:49+10:00"
# menu = "main"
title = "One App, One Repo"

+++

 There is a compromise on the one repo = one app, which is why we support Procfile within Cloud Foundry: that of the asynchronous worker. Logically, the worker (which consumes the queue) and the dispatch (which publishes to the queue) often *are* the same application, although they run in separate processes and perhaps separate containers. And they’re scaled differently.
