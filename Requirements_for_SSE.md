# Reuirements for System Security Engineering

###
###
### [Attack by Installing Add-Ons](Requirements_for_SSE.md)
###
###


## Use/Misuse Case 3: Attack by Installing Harmful Add-Ons

### Scenario
Mr Reynolds has an antique shop that houses some rare antiques from time to time. He chooses to use HA to control the access gates and cameras in his business place. He also uses supervisor applications to install add-ons which helps strengthen his security system and does some basic utilities. Ryan has a lot of knowledge in hacking and participates in hackathons. He finds out about a very expensive antique in Mr Reynolds collection. If he could somehow steal it and become very wealthy overnight by selling it on the black market. Ryan tries to find a weakness in the shop’s security system to figure out if the hassle is worth his time or not.

### Misuer
Ryan the hacker creates a harmful add-on to upload in the supervisor system. By careful observation, he knew if the add-on is about something that would enhance the security Mr Reynolds will definitely install the application without a second thought. 

![Attack by Installing Harmful Add-Ons](https://github.com/megharris/cyberockit/blob/main/images/AntiqueOwnerAddOnInstallation-2.png)
### Figure: Use/Misuse for Harmful Add-On attack

Ryan proceeds in building a harmful application and coats it inside a good looking application that would interest Mr Reynolds. He tries to get installed and control the home assistant system through his security application and steal the antique item easily. However, he faces a verification system that HA uses to verify add-ons before they are integrated into the main system of add-ons. Even after verification, clever malware can be hidden so manual testing is suggested for future HA add-ons. If Ryan fails to get into the HA supervisor he plans to send the link to an unauthorized download of security software by prompting Mr Reynolds with a real like website and everything. When Mr Reynolds will download from that application HA should detect its attempt to integrate with the system and warn the user to reconsider installing any unauthorized file. In this regard, it is slightly difficult because add-ons cannot run in the HA unless it is installed through the supervisor system. 
