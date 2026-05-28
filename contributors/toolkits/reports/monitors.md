---
description: >-
  Summary of the tools and techniques used to monitor the health of the Shift
  iQ platform
---

# Monitors

Here is a summary of the tools and techniques used to monitor the health of the Shift iQ platform:

* [UptimeRobot](https://status.shiftiq.com) monitors uptime 24x7x365.
* [Sentry](https://insite-systems.sentry.io) monitors errors and warnings, as well as overall application performance metrics.
* Microsoft IIS logs all incoming HTTP requests.
* [SmarterStats](https://stats.insite.com) analyzes IIS logs for comprehensive web traffic analytics.
* The InSite Timeline engine is a CQRS+ES implementation that logs every change to every aggregate in the application domain.

## SmarterStats

Note the SmarterStats server requires a reset from time to time. (After Microsoft Windows installs an update, it sometimes "forgets" to restart all the services in Windows, and a Windows admin needs to manually do that.) When a reset is needed, a server administrator on our end needs to do this.
