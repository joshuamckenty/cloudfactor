+++
Categories = ["Development", "GoLang"]
Description = ""
Tags = ["Development", "golang"]
date = "2015-09-17T13:52:51+10:00"
# menu = "main"
title = "Separation: Divide and Conquer"

+++

The separation should be “Config, Credentials, and Code”. Keeping Credentials in with other non-privileged config is endlessly problematic, especially in regulated environments where developers MUST NOT have access to prod credentials.

Also, while well-intentioned, the following statement is misleading:

'In a twelve-factor app, env vars are granular controls, each fully orthogonal to other env vars. They are never grouped together as "environments", but instead are independently managed for each deploy.'

In reality, for a production app, you WILL have logical groupings of configuration and credential values for "persistent" places-that-the-app-is-deployed, usually prod and staging, but perhaps other acceptance environments as well.

Whether you call these groupings of persistent place-that-the-app-is-deployed an "environment" or a "deploy" doesn't really matter that much, nor does how you manage the groupings, as long as you maintain the strict separation between Config, Credentials, and Code in every deploy/environment.
