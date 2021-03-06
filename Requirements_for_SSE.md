# Requirements for System Security Engineering

## Index
### SECTION ONE
* **[Remote Access](#case-1)**
* **[Brute Force Password Attack](#case-2)**
* **[Attack by Installing Add-Ons](#case-3)**
* **[IoT Device Risk](#case-4)**
* **[Abuse of System](#case-5)**

### SECTION TWO
* **[Security Related Configuration and Installation Issues](#security-related-configuration-and-installation-issues)**
* **[Reflection](#reflection)**
* **[Sources](#sources)**

## SECTION ONE

### Case 1
#### Remote Access
###### [Return to Top](#requirements-for-system-security-engineering)

#### Use Case
Max is a millionaire and has lot of cash at home. As he is a busy person most of his work is away from home. Max uses the home assistant system to control the hardware security system such as smart locks, security alarm, and security cameras. Remote access is the best way for Max to control the system and keep an eye on the activities. The main aim for Max is to be able to securely control the system remotely and get updates in regular time intervals. Max has several ways to use remote access such as port forwarding, VPN tunnel, or secure applications such as Nabu Case and DuckDNS.

#### Misuse Case
Attacker has an intention to rob Max’s home when he is away. To do so, Attacker should disable all the hardware security system used by Max. The main aim of attacker is to take access of home assistance remotely and deactivate the security system that will stop sending regular updates to Max. Attacker can achieve this by guessing password and exploiting the loopholes in the home assistance system used by Max.

#### Prevention and Security Requirement
Max can use security features to keep his system secure from attackers. Few such feature are as follows:
1.	Use secure application such as NabuCase and DuckDNS for remote access.
2.	Make sure to have terminal/SSH on the OS of Home assistance
3.	Use VPN Tunneling
4.	Port forwarding should be done on TCP protocol
5.	Enable Ip Ban while configuration of system
6.	Use strong password 

![Drawio Remote Access Image](https://github.com/megharris/cyberockit/blob/main/images/FinalRemoteAccess.png) 

**Figure: Use/Misuse for Remote Access Attack**

#### Alignment of Security Requirements with Advertised Features
* Use secure application such as NabuCase and DuckDNS for remote access: Yes
     * https://www.home-assistant.io/integrations/duckdns/
* Make sure to have terminal/SSH on the OS of Home assistance: Yes
     * https://www.home-assistant.io/docs/configuration/securing/#remote-access
     * https://www.home-assistant.io/blog/2017/11/02/secure-shell-tunnel/
* Use VPN Tunneling: Yes
     * https://www.home-assistant.io/docs/configuration/securing/#remote-access
     * https://pivpn.io/
* Port forwarding should be done on TCP protocol: Yes
     * https://www.home-assistant.io/integrations/fritz/#port-forward
* Enable IP Ban while configuration of system: Yes
     * https://www.home-assistant.io/integrations/http#ip-filtering-and-banning
* Use strong password


### Case 2
#### Password Attack
###### [Return to Top](#requirements-for-system-security-engineering)

#### Use Case
Matt owns a local manufacturing firm employing several employees. The business serves multiple large retail clients 
around the Midwest region like Menards and Bomgaars. Matt has a shop with warehouse space that holds all of their 
operational technology and significant volumes of high-value inventory. He also has a security system with cameras, an 
alarm, and automatic locks. He wants to take advantage of the convenience of using Home Assistant to control all of his 
operational technology, security system, thermostat, lighting, and POS system. As his business is growing, he recently 
installed and began using a computerized numerical controller (CNC) which is connected to Home Assistant through 
Modbus.

#### Misuse Case
Andrew is an IT professional in town who’s father was recently laid off from Matt’s business. Andrew knows that Matt started 
using Home Assistant to control all of his devices and decides this will be a good way to cause some havoc for Matt. He 
uses a brute force attack in order gain access to Matt’s Home Assistant, knowing that if he can change the password to prevent Matt from 
accessing and controlling the equipment, alarm system, thermostat, locks, and any other devices, he can cause some disruption 
in Matt's business. Once he gained access to Home Assistant, he found the Modbus add-on which is connected to a very expensive and very 
new piece of equipment, the CNC. Gaining control over the CNC device, Andrew changed the rotational speed of the machine and unlocked the safety 
guard on the machine which put other employees in the building at serious risk of entanglement and lacerations, 
fractures, amputations, and even death from ejected parts.

#### Prevention and Security Requirement
In order to prevent a brute force password attack from being successful, Home Assistant can protect its users by using a variety of controls. Logging activities would allow a Home Assistant user to review the logs for suspicious activity. However, if nefarious actors are aware that a logger exists, they could decide to hide activities from being logged. The user, provided they are reviewing the log, would then be unable to see the logged activities. One way to prevent attackers from hiding logging activities would be to require different login credentials for the logger feature. This would require that the attacker have two successful password hacks in order to gain access to Home Assistant and then again to gain access to the logged files. Home Assistant could develop additional layers of security to prevent brute force password attacks including account lockout for a certain number of unsuccessful login attempts, anomaly detection to determine if someone is logging into the system at an unusual time or in an unusual place, and multi-factor authentication to prevent even a good password for granting access and therefore control to the software. In the evvent that the attacker is unable to gain access to Home Assistant via a brute force password attack, Andrew could use a Network sniffer to try to intercept the login credentials. If by doing this, he is able to find the password and possibly a fingerprint or other utilizied type of MFA, then Matt could enable encryption for data transfers which would then mitigate the likelihood of sucess of using a Network Sniffer.

![Drawio Brute Force Password Image](https://github.com/megharris/cyberockit/blob/main/images/MisUseCase%20Matt%20%26%20Revenge%20Attack%20v7.PNG)

**Figure: Use/Misuse for Brute Force Password Attack**

#### Alignment of Security Requirements with Advertised Features
* Logger: Yes
     * https://www.home-assistant.io/docs/mqtt/logging/
* Logger-specific credentials: Possibly
     * https://www.home-assistant.io/docs/authentication/providers/
* Account lockout: Yes
     * https://www.home-assistant.io/docs/locked_out/
* Anomaly detection: No
* Multifactor authentication: Yes
     * https://www.home-assistant.io/docs/authentication/multi-factor-auth/
* Encrypted data transmissions: Yes
     * https://www.home-assistant.io/docs/mqtt/certificate/



### Case 3
#### Attack by Installing Harmful Add-Ons
###### [Return to Top](#requirements-for-system-security-engineering)

#### Use Case
Mr Reynolds has an antique shop that houses some rare antiques from time to time. He chooses to use HA to control the access gates and cameras in his business place. He also uses supervisor applications to install add-ons which helps strengthen his security system and does some basic utilities. Ryan has a lot of knowledge in hacking and participates in hackathons. He finds out about a very expensive antique in Mr Reynolds collection. If he could somehow steal it and become very wealthy overnight by selling it on the black market. Ryan tries to find a weakness in the shop’s security system to figure out if the hassle is worth his time or not.

#### Misuse Case
Ryan the hacker creates a harmful add-on to upload in the supervisor system. By careful observation, he knew if the add-on is about something that would enhance the security Mr Reynolds will definitely install the application without a second thought. 

Ryan develops a harmful application and coats it inside a good looking application that would interest Mr Reynolds. Next, he tries to get Mr Reynolds to install the application. When the application runs with HA Ryan, will control the HA system through it. It would make stealing the antique item very easy. However, he faces a verification system that HA uses to verify add-ons before they are integrated into the official store of add-ons.  Even after verification, some exploitable codes can be added to an authorized add-on so Manual testing should be done to increase security. Fortunately, for Ryan unauthorized add-ons can also be installed in HA. He posts the add-on in the unofficial HA add-ons list. All users are warned, that HA will not be responsible for the functionality and security of the unauthorized add-ons. Ryan chooses to upload his add-on application there and prompt Mr Reynolds to install the application by email. HA can also develop an automated scan before installation to warn Mr Reynolds about possible security issues with the application. When Mr Reynolds will download from the application HA should further detect its attempt to integrate with the system and warn the user to reconsider installing this unauthorized file. In this regard, Ryan will not succeed because the updated HA prevents most unauthorized intigrations from gaining control over useful user information. 

#### Prevention and Security Requirement

Few security features to keep the supervisor system secure from attackers are as follows:
1.	Manual add-on verification 
2.	Community push verification 
3.	Scan all the other applications in the system where HA is running
4.	Warn users of harmful add-ons before installation by running basic scans.
5.	Runs automatic virus scan before download 

![Attack by Installing Harmful Add-Ons](https://github.com/megharris/cyberockit/blob/main/images/AntiqueOwnerAddOnInstallation-2.png)

**Figure: Use/Misuse for Harmful Add-On attack**

#### Alignment of Security Requirements with Advertised Features
* Verification of Add-ons: Yes
     * https://www.home-assistant.io/addons/
* Manual Verification: Performed by Open Source Community
* Scan application before Installation: No
* Prevent unauthorized add-on to control HA: Yes after Update
     * https://www.home-assistant.io/blog/2021/01/22/security-disclosure/


### Case 4 
#### IoT Device 
###### [Return to Top](#requirements-for-system-security-engineering)

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

This misuse case could be prevented by notification when a new device is trying to connect to an already established IoT device. The assumption is that Frank would potentially 
be able to be near the premises to set up access on his own device (possibly a raspberry pi), and autoconnect to the thermostat. Secure monitoring and an 
alert system on Sherri’s UI might prevent Frank from being able to change the temperature and threshold settings. If Frank was able to turn off an alert 
set up by Sherri somehow there would need to be a reminder that the alert wasn’t on.

![misuse](https://user-images.githubusercontent.com/63809979/135000364-9309e84d-0d13-4cad-9b6d-cf758d37e55c.png)

**Figure: Use/Misuse for IoT Device**

#### Alignment of Security Requirements with Advertised Features
* Notification of new device: Yes
     * https://www.home-assistant.io/integrations/deconz/#requesting-support-for-new-device-trigger
* Secure monitoring: Yes
     * https://www.home-assistant.io/integrations/systemmonitor/
* Alert system: Yes
     * https://www.home-assistant.io/integrations/alert/
* Device Registry: Yes
     * https://developers.home-assistant.io/docs/device_registry_index/
* Second Home Assistant Instance: No
     * So far not much is available in the case of multiple Home Assistant set ups communicating with 
     each other, some users have requested being able to link multiple Home Assistants if needing to
     spread out the range, or connect devices that aren't allowed on another device. I can't find much
     documentation on security concerns for rogue Home Assistant users that are in close proximity to 
     another Home Assistant to autoconnect to the devices. This was the discussion on setting up multiple
     Home Assistant instances.
     https://github.com/home-assistant/architecture/issues/246

### Case 5
#### Abuse of System
###### [Return to Top](#requirements-for-system-security-engineering)

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

![misuse](https://github.com/megharris/cyberockit/blob/main/images/abuse%20of%20system%20v4.PNG)

**Figure: Use/Misuse for Abuse of System Device**

#### Alignment of Security Requirements with Advertised Features
* No – there is not really a part of the documentation that covers rogue IoT units. There is a section on duplicate entities but if (as is in the misuse case) there is a malicious user, then the system does not check that the devices are listed are the same ones that were originally configured. The below link is as close that I can find to a duplicate or rogue device, and it just is looking at log entries. 
     * https://www.home-assistant.io/integrations/knx/#duplicate-entities



## SECTION TWO

### Security Related Configuration and Installation Issues
###### [Return to Top](#requirements-for-system-security-engineering)

*	Blog posts of users helping users with configuration/install issues:
    * https://community.home-assistant.io/t/home-assistant-manual-security-system-with-xiaomi-gateway-as-siren/287916
    * This is one of many posts within the large blog site of users helping users. This and quite a few others are about security settings, but others are just about configuration for various apps and tools. HA staff add in to the discussions to make sure that there is good content and to help keep the blog strong, but they actively encourage user participation to fill in gaps and explore new horizons with the software as can be seen here https://community.home-assistant.io/t/editing-the-documentation-and-creating-a-pull-request-on-github/9573)
*	Documentation from Home Assistant about securing configuration and removing sensitive information from the system: https://www.home-assistant.io/docs/configuration/secrets/ 
*	At the bottom of all the instruction pages on the HA website, there is a call to action about writing documentation and helping others. There are links to the Blog, Github, and other parts of the instructions section, with the blog page being the liveliest. The Github page has a lot more direct code tweaking though. https://github.com/home-assistant/home-assistant.io/issues?utf8=%E2%9C%93&q=%22%2Fgetting-started%2Fautomation%2F%22&in=body
*	There is a variety of tools to help check changes that users make (Config checking tool https://www.home-assistant.io/docs/tools/check_config/) along with others to help improve user satisfaction with the software.
*	Overall HA makes a conscious effort to not only support but encourage community involvement with issues and making changes to the software. This effort is mostly focused on configuration and installation issues, and not as much on security issues. Though there is a section to report vulnerabilities, it is difficult to find previously patched fixes or known security issues that are being repaired. 
*  HA participated in [Hactoberfest](https://www.home-assistant.io/blog/2020/10/01/hacktoberfest-2020/) where they made a contest for contributors to find bugs and security flaws in their system. With the help of the contest they tried to use the open source community to run tests and detect security flaws, fix documentation and other problems which gets detected by the community
*  HA also encourage contributors to review each other’s pull requests before so their internal team can find more about the request from the get-go and makes their consideration to add or deny the requests easier.



### Reflection
###### [Return to Top](#requirements-for-system-security-engineering)

Each of the five team members contributed a scenario and use case diagram. We met twice to discuss the project, once before our instructor check-in and again once after. We also communicated via Slack and used a [Project Board](https://github.com/users/BigElkHunter/projects/1) to be sure we stayed on task. We planned to have our respective parts completed with enough time for each team member to review all of the other four cases. There has been a lot of discussion as we are all new to this type of modeling. It occurred to us after the project that many of our comments were exchanged via slack and we can better utilize the "comment" feature of Github for collaboration on future projects. For both of these team project submissions, we have collaborated well as a team but constantly found ways to improve for the next part of the project.

Individual Contributions:
* Jay Chavhan: Use case 1, review prevention and security requirements for use cases, attend team meetings and discuss scenarios
* Meg Harris: Use case 2, team reflection, organization, task delegation, review use cases and diagrams, attend team meetings and discuss scenarios
* Shifat Sarwar: Use case 3, create markdown file, review use cases, review prevention and security requirements for use cases, review security related configuration and installation issues, attend team meetings and discuss scenarios
* Noah Zetocha: Use case 4, review use cases and diagrams, attend team meetings and discuss scenarios
* Dylan Redden: Use case 5, prepare security related configuration and installation issues, attend team meetings and discuss scenarios

### Sources
###### [Return to Top](#requirements-for-system-security-engineering)

* https://community.home-assistant.io/t/home-assistant-manual-security-system-with-xiaomi-gateway-as-siren/287916
* https://community.home-assistant.io/t/editing-the-documentation-and-creating-a-pull-request-on-github/9573)
* https://www.home-assistant.io/docs/configuration/secrets/
* https://github.com/home-assistant/home-assistant.io/issues?utf8=%E2%9C%93&q=%22%2Fgetting-started%2Fautomation%2F%22&in=body
* https://www.home-assistant.io/docs/tools/check_config/
* https://www.home-assistant.io/blog/2020/10/01/hacktoberfest-2020/
