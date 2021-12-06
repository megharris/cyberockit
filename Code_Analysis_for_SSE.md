# Code Review Analysis

## Code Review Strategy

## Findings from Manual Code Review

### Authentication
#### CWE-778
According to an article at [opensource.com](https://github.com/home-assistant/core/blob/dev/homeassistant/components/logger/__init__.py), the logging function has many benefits including, but not limited to, separating _what_ is accomplished from just exactly _how_ it is accomplished. In our [Design](https://github.com/megharris/cyberockit/blob/main/Designing_for_SSE.md) project, we explained that the Microsoft Threat Modeling Tool identified a number of threats that were mitigated by establishing a logging or audit function. Home Assistant has the Logger integration which seems to address these issues. Due to the importance of keeping a log for so many reasons, we determined that [CWE 778: Insufficient Logging](https://cwe.mitre.org/data/definitions/778.html) was important to evaluate for Home Assistant, and really any other software. HA's [logger webpage](https://www.home-assistant.io/integrations/logger/) takes us to the code that is used to invoke this feature. We reviewed the [init file](https://github.com/home-assistant/core/blob/dev/homeassistant/components/logger/__init__.py) and found that it is actually invoking the Python Logging module in line 2, which is powerful, thread-safe and meets the needs of various types of users, individual and enterprise. 

![image](https://user-images.githubusercontent.com/54555836/144769870-b1625897-8fa1-4c2c-bf9c-a90c64a7d379.png)


#### CWE-307
The HTTP integration of HA is implemented in all active installations. This integration includes an IP ban and a threshold for failed login attempts. This can be found in the [ban.py](https://github.com/home-assistant/core/blob/dev/homeassistant/components/http/ban.py) file. The file also notes that the user-agent is unsanitized which could certainly create vulnerabilities for SQL injection and XSS. However, the user-agent data is only included in the log, preventing these issues. No significant findings for this file/CWE.

![image](https://user-images.githubusercontent.com/54555836/144769712-f9c59319-2d91-444d-9910-9ba5d4177870.png)


CWE authentication manual code review
The code for authentication is well structured. Comments and docstrings are used to explain the code. Looking at the auth_store.py file, creating the new user, adding credentials, removing user, updating credentials, activating, and deactivating users is done properly. Proper use of async, assert, and await keywords is done. Using these keywords helps program to be synchronous and waits for the other callback function to complete its existing loop thus, avoiding the inconsistency in the storage. Exception handling in auth_store.py could have been used for each function. For example, Exception handling for creating new user can be added. Though, exception handling for providing wrong group id is implemented. Removing the user is done by pop operation on the user id but other credentials should also be removed. 
Looking at the _init_.py which is used to provide an authentication layer for Home Assistant. Exception handling is used in necessary parts. Classes for invalid authentication error and invalid provider are left blank without any body. These classes could have included the count for the invalid authentication from same Ip address so that, multiple log-in attempts from same Ip could be banned. 

![Alt text](ss-1.png)

#### CWE-287
In providers, _init_.py the authentication provider functions and multifactor authentication provider function are defined. CWE-287 – improper authentication cannot be valid. As authentication is done properly. In CWE-287, remembering the cookies for the credentials is the problem, but in this code no cookies where remembered and also multifactor authentication is used. Exception handling for these functions is also implemented.

![Alt text](ss-2.png)

#### CWE-291
Reliance on IP Address for Authentication can be a valid CWE for Home Assistant. Home Assistant relies on the trusted network IP addresses to bypass the log-in without any credentials. As per CWE-291, relying on the IP address to bypass the log-in can be harmful. I addresses can easily be spoofed. At least the multifactor authentication should be implemented while allowing trusted networks to bypass the log-in. Code for trusted network is found under providers folder, trusted_network.py. 

![Alt text](ss-4.png) 
![Alt text](ss-3.png)

Changing the return value to True can enable the multifactor authentication for trusted network. 
#### CWE-916
Use of Password Hash with Insufficient Computational Effort. The CWE-916 specifies that using password hash function with insufficient computational effort can be harmful as many hash functions execute quickly with minimal overhead. CWE-916 suggests few hash functions that should be used such as bcrypt, scrypt, and PBKDF2 because they are all stronger than using salts with hash functions with very little computing overhead. 
Home Assistant uses one of the suggested hash functions by the CEW-916 that is bcrypt.

![Alt text](ss-5.png)

The code for this is found in Homeassistant.py file which provides authentication. 
#### CWE-308
Use of Single-factor Authentication. According to CWE-308, single-factor authentication can lead to unnecessary risk. Home assistant uses multifactor authentication which minimizes this risk. Home assistant provides max three trails for mfa. 

![Alt text](ss-6.png)

Code for this can be found at Core/homeassistant/auth/mfa_modules/_init_.py


### IoT Devices
#### CWE 1196

### Add-Ons
#### CWE-20

![](https://github.com/megharris/cyberockit/blob/main/CodeReview/images/cwe20.png)

In Supervisor/addon/addon.py [CWE- 319 – Cleartext transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html) is not a valid case as sensitive information (login credentials in this case) are not transmitted from supervisor to the add-on. Instead, a token is checked validity, for an add-on to start. The token is issued when supervisor is logged into by the user or by a service. This stops the credentials from needing to be entered in add-ons which may or may not be validated by the add-on store. Since the credentials only need to be entered in Supervisor, they are not transmitted over the network. The token is changed for each instance that Supervisor is logged in or an application is requested to start up.  

#### CWE-319

![](https://github.com/megharris/cyberockit/blob/main/CodeReview/images/cwe319.png)

## Findings from Automated Code Review


## Summary of Key Findings

## OSS Project Pull Requests, Issues, Discussions
The lead developers at Home Assistant take a very active role in the open-source community. This includes monthly blog updates, software bug fixes and code revisions. Community involvement in open-source software development is highly celebrated by the Home Assistant team, and the lead developers actively participate in the community engagement. Recently a hack-a-thon called Hacktoberfest was held as a way of celebrating open-source software and people contributing to open-source software (especially Home Assistant) in which many different changes to Home Assistant were made by volunteer developers. There is also the upcoming annual Home Assistant State-of-the-Union, where the lead developers for Home Assistant share their vision and plans for the next year, along with new features that they have been working on over the last year. 

## Reflection and Collaboration
