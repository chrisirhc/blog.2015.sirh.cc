---
layout: post
title: Challenges in logging JavaScript errors
---

How to remove noise from false positives?

Key issues:
- Script load got aborted
- User navigates away from page

How to detect if all the scripts were loaded?
- Check if all scripts were loaded
- How?
- Add an onload event for each script
- Detecting for the stop button.

- User navigates away from page and causes tpload error
  - don't log errors that come after beforeunload event was fired
