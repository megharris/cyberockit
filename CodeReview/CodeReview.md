## Authentication

According to an article at [opensource.com](https://github.com/home-assistant/core/blob/dev/homeassistant/components/logger/__init__.py), the logging function has many benefits including, but not limited to, separating what isg accomplished from just exactly how it is accomplished. In our Design project, we explained that the Microsoft Threat Modeling Tool identified a number of threats that were mitigated by establishing a logging or audit function. Home Assistant has the Logger integration which seems to address these issues. Due to the importance of keeping a log for so many reasons, we determined that [CWE 778: Insufficient Logging](https://cwe.mitre.org/data/definitions/778.html) was important to evaluate for Home Assistant, and really any other software. HA's [logger webpage](https://www.home-assistant.io/integrations/logger/) takes us to the code that is used to invoke this feature. We reviewed the [init file](https://github.com/home-assistant/core/blob/dev/homeassistant/components/logger/__init__.py) and found that it is actually invoking the Python Logging module in line 2, which is powerful, thread-safe and meets the needs of various types of users.

There are many Add-on applications that Home Assistant can download, and as such analyzing all of them is out of the scope of this project. While there is little attack surface for improper input which could lead to an injection attack, there are still small sections that require input validation. In Websocket.py there is an entry for messages into the web socket API, which must be checked. [CWE-20  -- Improper Input Validation](https://cwe.mitre.org/data/definitions/20.html) is not valid in this case, as input is ran against a filter to verify that the input is of a specific JSON type. Exception logging is also handled in this script.

## Add-ons

CWE-20

![](https://github.com/megharris/cyberockit/blob/main/CodeReview/images/cwe20.png)

In Supervisor/addon/addon.py [CWE- 319 – Cleartext transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html) is not a valid case as sensitive information (login credentials in this case) are not transmitted from supervisor to the add-on. Instead, a token is checked validity, for an add-on to start. The token is issued when supervisor is logged into by the user or by a service. This stops the credentials from needing to be entered in add-ons which may or may not be validated by the add-on store. Since the credentials only need to be entered in Supervisor, they are not transmitted over the network. The token is changed for each instance that Supervisor is logged in or an application is requested to start up.  

CWE-319

![](https://github.com/megharris/cyberockit/blob/main/CodeReview/images/cwe319.png)


## Ongoing Contributions

The lead developers at Home Assistant take a very active role in the open-source community. This includes monthly blog updates, software bug fixes and code revisions. Community involvement in open-source software development is highly celebrated by the Home Assistant team, and the lead developers actively participate in the community engagement. Recently a hack-a-thon called Hacktoberfest was held as a way of celebrating open-source software and people contributing to open-source software (especially Home Assistant) in which many different changes to Home Assistant were made by volunteer developers. There is also the upcoming annual Home Assistant State-of-the-Union, where the lead developers for Home Assistant share their vision and plans for the next year, along with new features that they have been working on over the last year. 
