+++
Categories = ["Development", "GoLang"]
Description = ""
Tags = ["Development", "golang"]
date = "2015-09-17T13:52:51+10:00"
# menu = "main"
title = "Separation: Divide and Conquer"

+++

The separation should be “Config, Credentials, and Code”. Keeping Credentials in with other non-privileged config is endlessly problematic, especially in regulated environments where developers MUST NOT have access to prod credentials.
