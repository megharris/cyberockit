# Requirements for System Security Engineering

## PART 1

### [Remote Access](#case-1)
### [Brute Force Password Attack](#case-2)
### [Attack by Installing Add-Ons](#case-3)
### [IoT Device Risk](#case-4)
### [Abuse of System](###case-5)

### Case 1
#### Remote Access

#### Use Case
Max is a millionaire and has lot of cash at home. As he is busy person most of his work is away from home. Max uses home assistance system to control the hardware security system such as smart locks, security alarm and security cameras. Remote access is best way for Max to control the system and keep an eye on the activities. The main aim for Max is to be able to securely control the system remotely and get updates in regular time intervals. Max has several ways to use remote access such as port forwarding, VPN tunnel, or secure applications such as Nabu Case and DuckDNS.

#### Misuse Case
Attacker has an intention to rob Max’s home when he is away. To do so, Attacker should disable all the hardware security system used by Max. The main aim of attacker is to take access of home assistance remotely and deactivate the security system that will stop sending regular updates to Max. Attacker can achieve this by guessing password and exploiting the loopholes in the home assistance system used by Max.

![Drawio Remote Access Image](https://github.com/megharris/cyberockit/blob/main/images/remoteAccess.png)

**Figure: Use/Misuse for Remote Access Attack**

#### Prevention and Security Requirement

Max can use security features to keep his system secure from attackers. Few such feature are as follows:
1.	Use secure application such as NabuCase and DuckDNS for remote access.
2.	Make sure to have terminal/SSH on the OS of Home assistance
3.	Use VPN Tunneling
4.	Port forwarding should be done on TCP protocol
5.	Enable Ip Ban while configuration of system
6.	Use strong password 

### Case 2
#### Brute Force Password Attack

#### Use Case
Matt owns a local manufacturing firm employing several employees. The business serves multiple large retail clients 
around the Midwest region like Menards and Bomgaars. Matt has a shop with warehouse space that holds all of their 
operational technology and significant volumes of high-value inventory. He also has a security system with cameras, an 
alarm, and automatic locks. He wants to take advantage of the convenience of using Home Assistant to control all of his 
operational technology, security system, thermostat, lighting, and POS system. As his business is growing, he recently 
installed and began using a computerized numerical controller (CNC) which is connected to Home Assistant through 
Modbus.

#### Misuse Case
Andrew is a hacker in town who’s father was recently laid off from Matt’s business. Andrew knows that Matt started 
using Home Assistant to control all of his devices and decides this will be a good way to cause some havoc for Matt. He 
uses a brute force attack in order gain access to Matt’s Home Assistant to infect some of Matt’s devices with Malware. 
Once he gained access to Home Assistant, he found the Modbus add-on which is connected to a very expensive and very 
new piece of equipment, the CNC. Andrew installed the malware on the CNC and several other connected devices. 
Gaining control over the CNC device, Andrew changed the rotational speed of the machine and unlocked the safety 
guard on the machine which put other employees in the building at serious risk of entanglement and lacerations, 
fractures, amputations, or even death from ejected parts.

![Drawio Brute Force Password Image](https://github.com/megharris/cyberockit/blob/main/images/MisUseCase%20Matt%20%26%20Revenge%20Attack%20CLEAN.PNG)

**Figure: Use/Misuse for Brute Force Password Attack**

#### Prevention and Security Requirement

NEED TO FILL THIS IN!!!!

### Case 3
#### Attack by Installing Harmful Add-Ons

#### Use Case
Mr Reynolds has an antique shop that houses some rare antiques from time to time. He chooses to use HA to control the access gates and cameras in his business place. He also uses supervisor applications to install add-ons which helps strengthen his security system and does some basic utilities. Ryan has a lot of knowledge in hacking and participates in hackathons. He finds out about a very expensive antique in Mr Reynolds collection. If he could somehow steal it and become very wealthy overnight by selling it on the black market. Ryan tries to find a weakness in the shop’s security system to figure out if the hassle is worth his time or not.

#### Misuse Case
Ryan the hacker creates a harmful add-on to upload in the supervisor system. By careful observation, he knew if the add-on is about something that would enhance the security Mr Reynolds will definitely install the application without a second thought. 
Ryan proceeds in building a harmful application and coats it inside a good looking application that would interest Mr Reynolds. He tries to get installed and control the home assistant system through his security application and steal the antique item easily. However, he faces a verification system that HA uses to verify add-ons before they are integrated into the main system of add-ons. Even after verification, clever malware can be hidden so manual testing is suggested for future HA add-ons. If Ryan fails to get into the HA supervisor he plans to send the link to an unauthorized download of security software by prompting Mr Reynolds with a real like website and everything. When Mr Reynolds will download from that application HA should detect its attempt to integrate with the system and warn the user to reconsider installing any unauthorized file. In this regard, it is slightly difficult because add-ons cannot run in the HA unless it is installed through the supervisor system. 

#### Prevention and Security Requirement

NEED TO FILL THIS IN!!!!!

![Attack by Installing Harmful Add-Ons](https://github.com/megharris/cyberockit/blob/main/images/AntiqueOwnerAddOnInstallation-2.png)

**Figure: Use/Misuse for Harmful Add-On attack**

### Case 4 
#### IoT Device 

#### Use Case
Sherri owns a small hazardous material processing company. The business serves multiple clients around her region and she has a warehouse space that is 
integral to the company function. The company’s focus is on environmental protection. One of their main functions is picking up waste from high quantity 
generators and neutralizing large quantities of hazardous chemicals, before shipping it to chemical processing plant. Given the cost saving of using a 
free open source product like Home Assistant, Sherri wants to set up her warehouse to have automatic temperature ranges and better physical security 
with cameras and automatic locks. Sherri buys various IoT locks, cameras and a thermostat system for monitoring and maintaining the temperature of the 
space, by adding cards to her Home Assistant interface. She uses Home Assistant Supervisor to manage the add-ons for the IoT devices 
she uses. She sets up multiple users for her employees to access the software. She also configures an alert on her Home Assistant UI if the temperature
falls outside the threshold settings.

#### Misuse Case
Sherri is discussing her new Home Assistant setup with her sister at the hardware store. They are talking about the temperature needed to maintain the 
chemicals being stored in the warehouse and about how Home Assistant has helped improve security. Frank, an arsonist and amateur hacker overhears the 
conversation and decides to research Home Assistant, and look up the small business address. Frank wants to connect his device to the thermostat directly.
On a particularly hot day in late July, after observing everyone leave, he attempts to connect directly to the thermostat. He quickly changes the setting 
of the device to its highest temperature. 
Frank’s plan is to increase the temperature in the warehouse to a point where one of the ignitable chemicals in storage heats to its flashpoint. At this 
temperature, one of the small bottles ignites and it quickly spreads to other ignitable chemicals. Frank watches the warehouse go up in flames. Some of 
the other chemicals that weren’t burned off leach into the groundwater and contaminate the region.

#### Prevention and Security Requirement

This misuse case could be prevented by notification when a new device is trying to connect to a IoT device. The assumption is that Frank would potentially 
be able to be near the premises to set up access on his own device (possibly a raspberry pi), and autoconnect to the thermostat. Secure monitoring and an 
alert system on Sherri’s UI might prevent Frank from being able to change the temperature and threshold settings. If Frank was able to turn off an alert 
set up by Sherri somehow there would need to be a reminder that the alert wasn’t on.

![misuse](https://user-images.githubusercontent.com/63809979/134778061-7c182401-b10f-4b32-825a-ca5d2ceb3f0c.png)

**Figure: Use/Misuse for IoT Device**

### Case 5
#### Abuse of System

#### Use Case
Alice is the owner of the coffee shop C@ff1n3 Dr3@ms, and she uses Home Assistant (HA) to control 
her businesses IoT devices. The IoT devices she uses at the coffee shop are a smart thermostat, 
and a smart utility meter to help regulate the climate control system and monitor her business’ 
power consumption. The power meter will adjust the climate control systems heating and cooling 
program to stop it from using to much power during peak times.

#### Misuse Case
Bob is a disgruntled barista that is upset with how busy the coffee shop is, and that he does not
get the days off that he wants. To help solve his issue of being too busy without enough help, 
Bob decides to buy the same smart thermostat and utility meter. Since Alice puts all her IoT devices
on the same wi-fi network that she lets the guests use, Bob is easily aware of the password 
to the network. As he adds the devices to the network, Home Assistant notices them on the network
and adds them to its list of devices. Since HA communicates to the devices via mDNS (a UDP based 
protocol) HA does not get back an acknowledgement that the message went to the correct device. 
Bob switches the hostname on the original smart thermostat (Thermostat A) with the one he bought 
(Thermostat B) but does not attach Thermostat B to the climate control system. The result is that 
when HA changes the temperature to match the heating or cooling program the climate system does 
not respond to the message, as Thermostat B receives the mDNS packet for this. This causes guests 
to leave the coffee shop due to the climate being uncomfortable. Bob hides Thermostat B inside the 
coffee shop so that HA will still notice it on the network, but in a place that Alice is unlikely 
to find it. 
Bob does a similar malicious action with the smart utility meter. Switching the hostnames with the
one he bought and hides the one he bought within the coffee shop so that HA does not notice it is 
gone. The result is that the original utility meter will continue to receive messages to lower the
power consumption from the smart thermostat. Since the original meter is not connected to the utility
lines it will not be able to shutdown the higher than ordered power consumption. 
Security Requirement to mitigate risk:
1.	To mitigate this risk MFA for adding any new device to the HA system needs to be implemented. 
This will stop rogue IoT devices from being added without the system owner’s knowledge. 
2.	To mitigate the risk of this mDNS attack, change the method that HA communicates to the IoT devices 
to TCP. Changing to TCP would allow HA to receive back an acknowledgement that the message was received 
by the correct host MAC. This will require changing from mDNS to DNS as a means of sending out packets
from HA to the IoT devices. 
    a.	HA could also verify the DNS packets via MAC addresses instead of hostnames. 
3.	To further mitigate risk, communication verification from HA to the end devices would verify that the commands were received by the correct devices. 

#### Prevention and Security Requirement

No – there is not really a part of the documentation that covers rogue IoT units. There is a section on duplicate entities but if (as is in the misuse case) there is a malicious user, then the system does not check that the devices are listed are the same ones that were originally configured. The below link is as close that I can find to a duplicate or rogue device, and it just is looking at log entries. https://www.home-assistant.io/integrations/knx/#duplicate-entities

![misuse](https://github.com/megharris/cyberockit/blob/main/images/abuseofsystem.drawio.png)

**Figure: Use/Misuse for Abuse of System Device**


## PART 2

*	Blog posts of users helping users with configuration/install issues:
    * https://community.home-assistant.io/t/home-assistant-manual-security-system-with-xiaomi-gateway-as-siren/287916
    * This is one of many posts within the large blog site of users helping users. This and quite a few others are about security settings, but others are just about configuration for various apps and tools. HA staff add in to the discussions to make sure that there is good content and to help keep the blog strong, but they actively encourage user participation to fill in gaps and explore new horizons with the software as can be seen here https://community.home-assistant.io/t/editing-the-documentation-and-creating-a-pull-request-on-github/9573)
*	Documentation from Home Assistant about securing configuration and removing sensitive information from the system: https://www.home-assistant.io/docs/configuration/secrets/ 
*	At the bottom of all the instruction pages on the HA website, there is a call to action about writing documentation and helping others. There are links to the Blog, Github, and other parts of the instructions section, with the blog page being the liveliest. The Github page has a lot more direct code tweaking though. https://github.com/home-assistant/home-assistant.io/issues?utf8=%E2%9C%93&q=%22%2Fgetting-started%2Fautomation%2F%22&in=body
*	There is a variety of tools to help check changes that users make (Config checking tool https://www.home-assistant.io/docs/tools/check_config/) along with others to help improve user satisfaction with the software.
*	Overall HA makes a conscious effort to not only support but encourage community involvement with issues and making changes to the software. This effort is mostly focused on configuration and installation issues, and not as much on security issues. Though there is a section to report vulnerabilities, it is difficult to find previously patched fixes or known security issues that are being repaired. 
