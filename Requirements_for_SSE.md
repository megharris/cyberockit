# Reuirements for System Security Engineering

###
###
### [Attack by Installing Add-Ons](#case-3)
### [ffff](#case-4)
###


## Case 3
### Attack by Installing Harmful Add-Ons

### Scenario
Mr Reynolds has an antique shop that houses some rare antiques from time to time. He chooses to use HA to control the access gates and cameras in his business place. He also uses supervisor applications to install add-ons which helps strengthen his security system and does some basic utilities. Ryan has a lot of knowledge in hacking and participates in hackathons. He finds out about a very expensive antique in Mr Reynolds collection. If he could somehow steal it and become very wealthy overnight by selling it on the black market. Ryan tries to find a weakness in the shop’s security system to figure out if the hassle is worth his time or not.

### Misuser
Ryan the hacker creates a harmful add-on to upload in the supervisor system. By careful observation, he knew if the add-on is about something that would enhance the security Mr Reynolds will definitely install the application without a second thought. 

![Attack by Installing Harmful Add-Ons](https://github.com/megharris/cyberockit/blob/main/images/AntiqueOwnerAddOnInstallation-2.png)
### Figure: Use/Misuse for Harmful Add-On attack

Ryan proceeds in building a harmful application and coats it inside a good looking application that would interest Mr Reynolds. He tries to get installed and control the home assistant system through his security application and steal the antique item easily. However, he faces a verification system that HA uses to verify add-ons before they are integrated into the main system of add-ons. Even after verification, clever malware can be hidden so manual testing is suggested for future HA add-ons. If Ryan fails to get into the HA supervisor he plans to send the link to an unauthorized download of security software by prompting Mr Reynolds with a real like website and everything. When Mr Reynolds will download from that application HA should detect its attempt to integrate with the system and warn the user to reconsider installing any unauthorized file. In this regard, it is slightly difficult because add-ons cannot run in the HA unless it is installed through the supervisor system. 

## Case 4 

Sherri owns a small hazardous material processing company. The business serves multiple clients around her region and she has a warehouse space that is 
integral to the company function. The company’s focus is on environmental protection. One of their main functions is picking up waste from high quantity 
generators and neutralizing large quantities of hazardous chemicals, before shipping it to chemical processing plant. Given the cost saving of using a 
free open source product like Home Assistant, Sherri wants to set up her warehouse to have automatic temperature ranges and better physical security 
with cameras and automatic locks. Sherri buys various IoT locks, cameras and a thermostat system for monitoring and maintaining the temperature of the 
space, by adding cards to her Home Assistant interface. She uses Home Assistant Supervisor to manage the add-ons for the IoT devices 
she uses. She sets up multiple users for her employees to access the software. She also configures an alert on her Home Assistant UI if the temperature
falls outside the threshold settings.

**Misuse Case**

Sherri is discussing her new Home Assistant setup with her sister at the hardware store. They are talking about the temperature needed to maintain the 
chemicals being stored in the warehouse and about how Home Assistant has helped improve security. Frank, an arsonist and amateur hacker overhears the 
conversation and decides to research Home Assistant, and look up the small business address. Frank wants to connect his device to the thermostat directly.
On a particularly hot day in late July, after observing everyone leave, he attempts to connect directly to the thermostat. He quickly changes the setting 
of the device to its highest temperature. 
Frank’s plan is to increase the temperature in the warehouse to a point where one of the ignitable chemicals in storage heats to its flashpoint. At this 
temperature, one of the small bottles ignites and it quickly spreads to other ignitable chemicals. Frank watches the warehouse go up in flames. Some of 
the other chemicals that weren’t burned off leach into the groundwater and contaminate the region.

**Prevention and Security Requirement**

This misuse case could be prevented by notification when a new device is trying to connect to a IoT device. The assumption is that Frank would potentially 
be able to be near the premises to set up access on his own device (possibly a raspberry pi), and autoconnect to the thermostat. Secure monitoring and an 
alert system on Sherri’s UI might prevent Frank from being able to change the temperature and threshold settings. If Frank was able to turn off an alert 
set up by Sherri somehow there would need to be a reminder that the alert wasn’t on.

<br>

![misuse](https://user-images.githubusercontent.com/63809979/134778061-7c182401-b10f-4b32-825a-ca5d2ceb3f0c.png)
