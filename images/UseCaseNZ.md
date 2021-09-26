
**Use Case**

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
