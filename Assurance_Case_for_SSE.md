# Assurance Case for System Security Engineering

## Index
### SECTION ONE
* **[Remote Access](#case-1)**
* **[Brute Force Password Attack](#case-2)**
* **[Attack by Installing Add-Ons](#case-3)**
* **[IoT Device Risk](#case-4)**
* **[Abuse of System](#case-5)**

### SECTION TWO
* **[Reflection](#reflection)**


## SECTION ONE

### Case 1
#### Remote Access
###### [Return to Top](#assurance-case-for-system-security-engineering)

![Assurance Case Jay](https://github.com/megharris/cyberockit/blob/main/images/JayChavhanAssuranceCaseUpdatedV3.png)

#### Evidence for Assurance Case - Jay

E1: DuckDNS is introduced in HA 0.55:
Port-forwarding is one of the best way for remote access. HTTPS encryption is required for secured port-forwarding. DuckDNS provides HTTPS encryption and single URL to access HA remotely.

https://www.home-assistant.io/integrations/duckdns/ 
https://github.com/home-assistant/core/tree/dev/homeassistant/components/duckdns

E2: Configuration documentation for remote access providing SSH manual:
SSH provides more privacy and security. Using SSH/Terminal is beneficial to Undo the changes which were done by mistake.

https://www.home-assistant.io/blog/2017/11/02/secure-shell-tunnel/
https://www.home-assistant.io/docs/configuration/securing/#remote-access 

E3: Configuration documentation for VPN:
Using VPN provides the encryption for the links between devices and network. Documentation provides the correct way to implement it.

https://www.home-assistant.io/docs/configuration/securing/#remote-access. For more infromation [click here](https://pivpn.io/)

E4: IP filtering and banning documentation explains the concept of IP address filtering and banning them when hacker tries to attempt different passwords for several times.

https://www.home-assistant.io/integrations/http#ip-filtering-and-banning 

E5: For evidence 5 IP_bans.yaml shows the status of Ip ban (enabled/disabled). This should be set to enabled by default. Brute force attacks can be prevented by enabling Ip ban. Set Ip_ban_enabled to true and maximum number of attempts. After first ban, ip_ban.yaml file is created in configuration folder. Notification to HA is also sent.

### Case 2
#### Brute Force Password Attack
###### [Return to Top](#assurance-case-for-system-security-engineering)

![Assurance Case Meg](https://github.com/megharris/cyberockit/blob/main/images/Assurance%20Case%202%20V7.png)
#### Evidence for Assurance Case - Meg

E1: Past User Experiences:
Users have not experienced access attacks using HTTP Response Body Manipulation. The evidence of this is the lack of claims or complaints from users.

E2: HA TOTP Policy:
HA's configuration policy allows the user to enable time-based one-time password (TOTP) with an expiration time of 30 seconds.
[HA TOTP Policy](https://www.home-assistant.io/docs/authentication/multi-factor-auth/#setting-up-totp)

E3: OTP Policy:
HA's configuration policy allows the user to enable time-based one-time password (TOTP) that is invalidated after one use and has an expiration time of 30 seconds.
[HA OTP Policy](https://www.home-assistant.io/integrations/otp/)

E4: Configuration Policy:
HA's configuration policy has a counter integration does not make the counter variable accessible to the client side.
[Counter Integration](https://www.home-assistant.io/integrations/counter/)

E5: HA Website Prefix:
HA's website prefix has https:// indicating use of SSL/TSL encryption.
https://www.home-assistant.io/

E6: Configuration Policy:
There is no evidence that HA does not rely on the response body returned by the server or that the system validates against response manipulation. This is certainly one suggestion we could make to HA. 


### Case 3
#### Attack by Installing Harmful Add-Ons
###### [Return to Top](#assurance-case-for-system-security-engineering)

![Assurance Case Shifat](https://github.com/megharris/cyberockit/blob/main/images/updated_assurance_case_add_on_installation_v2.png)
#### Evidence for Assurance Case - Shifat

E1: Security Ratings on Add-Ons
The security documentation of Add-Ons specifies that all available add-ons from open source community are tested and graded for security. The users are advised to only install lower graded add-ons if they trust the source. This grading is visible to anyone downloading the add-ons directly from the supervisor store. 
[Add-On Security Documentation](https://developers.home-assistant.io/docs/add-ons/security)

E2: Verification Procedure Documentation
Although the previous documentation says that an add-on with a grade of 6 is harmless for anyone to download. There is no available documentation which shows how HA actually performs this verification before making them available for people to download. 

E3: Harmful Add-On Attack Test Results
The function is said to be available on HA by default. It talks about running the add-ons in a protection enable mode which stops them from getting any unauthorized control over the system. [Add-On Security Documentation](https://developers.home-assistant.io/docs/add-ons/security). However, no documentation for conducted tests are available which clearly shows the available function to be sufficient in stopping add-ons from getting control.

E4: Add-On Compatibility Documents
The following page [Install addons on the docker without supervisor](https://community.home-assistant.io/t/can-i-install-addons-on-the-docker-installation-not-supervised/281022) provides an official answer to installing add-ons from unauthorized sources. According to them, the add-ons will not work with HA if it is installed through other methods. However, a users in Reddit talks about a way to install and run addons using their own docker containers [link](https://www.reddit.com/r/homeassistant/comments/imv0yc/home_assistant_addons_without_supervisor/), which takes us to evidence 5.

E5: Add-On Installation Guide
HA provides more answers in their [add-on installation guide Q/A](https://community.home-assistant.io/t/ha-docker-container-installing-addons/305947). Here, they answer that a user has to manage their own containerized applications if they choose to run add-ons using their own docker container. Without supervisor they will not be able to access the official add-on store as well. 

### Case 4 
#### IoT Device 
###### [Return to Top](#assurance-case-for-system-security-engineering)

![assuranceCaseNZ_V7](https://user-images.githubusercontent.com/63809979/136719199-c01f6369-f5b8-446b-a210-1dfe355c642c.png)
#### Evidence for Assurance Case - Noah
E1 and E2: As discussed in more detail in the other assurance cases, basic password access to the interface and multi-factor authentication provides adequate protection for mis-use of IoT device control in the user interface. 

E3: [This](https://community.home-assistant.io/t/master-ha-instance-with-multiple-slaves/109849/2) is a community thread about setting up a master with secondary Home Assistants. Some users want to set up another instance of Home Assistant to track multiple locations or extend the range within one location. The evidence E3 used here is linked device notification when using multiple Home Assistants.  There is some documentation on multiple Home Assistant instances communicating via MQTT, as available in a question [here](https://community.home-assistant.io/t/two-ha-instances-how-to-communicate-between-them/30877). There remains some uncertainty whether or not a misuser could then use another Home Assistant instance to communicate with IoT devices, though this would depend on the mis-user being on premises. Given the communication has to be set up by the user and it is not automatic raises some issues if the mis-user is at the location. The conversation on multiple instances is available [here](https://github.com/home-assistant/architecture/issues/246).

E4: Home assistant allows the user to connect and use IoT devices within their home or work. By editing the configuration.yaml file, the user can set automatic alerts, and threshold settings for things like temperature, that they want to keep within a certain range. Setting up this connection with the IoT devices can be done via the user interface through the configurable yaml file. Issues with connection can be solved with [tutorials available](https://www.home-assistant.io/docs/configuration/devices), as seen in evidence 4. 

E5 and E6: Evidence 5 and 6 discuss lost connection alerts, and automatic reconnects, as seen [here](https://community.home-assistant.io/t/simple-mobile-notification-when-device-becomes-unavailable/255239). Given the issues of mis-users trying to control user IoT devices, there is security enabled for some of the issues raised. Alert integrations can be seen [here](https://www.home-assistant.io/integrations/alert/). Alerts can be set up in various capacities to alert the Home Assistant owners to changes in the state of their location. Certain integrations have lost connection alerts and settings, that provide a reasonable process of alerting and then trying to reconnect to the IoT device. This can be seen in the Homematic integration for [lost connection](https://www.home-assistant.io/integrations/homematic/#detecting-lost-connections).

### Case 5
#### Abuse of System
###### [Return to Top](#assurance-case-for-system-security-engineering)

![Assurance Case Dylan](https://github.com/megharris/cyberockit/blob/main/images/DylanAssuranceCaseV5.drawio.png)

#### Evidence for Assurance Case – Dylan

E1: https://www.home-assistant.io/integrations/nest/#climate
	The Home Assistant (HA) Nest smart thermostat documentation shows how the device is authenticated each time a new one is added to HA. This is repeated for many different IoT devices, but Nest’s documentation is the cleanest one we were able to find. This shows that Sub-Claim C3 is correct, though without an exhaustive search of the thousands of devices that are compatible with HA it cannot be stated that all devices must be authenticated the same way. The importance of this evidence is that it does show that authentication is possible for new devices within HA, and could be applied to all other devices, if HA so chose to make it a requirement for any device’s application in the HA app store.

E2: NA 
	Despite an exhaustive search was conducted on HA documentation, a definitive statement on how HA references devices that it is connected to could not be found. This could be from the vast number of devices that HA is compatible with, but nothing could be found regarding how HA references devices by IP address, MAC address, or IMEI. Within some HA documentation about connecting a specific device it is stated that the device is merely identified by a user assigned “client_id”, but nothing else. If this evidence was found within the HA documentation the argument would be greatly improved, and security would be much more assured as the mode of communication between HA Core and the devices it controls needs to be standardized in order to ensure security within its network.

E3: https://www.home-assistant.io/integrations/tcp/
	UDP is not directly stated to be the default means of layer 4 communication for HA, the referenced documentation states that TCP is an optional alternative. This means that UDP is the default protocol that HA uses to communicate. While this is understandable to keep the local network clear and the communication quick, this lacks the ability for HA to verify that the commands it is sending are received by the correct device, or received at all. 

E4: NA 
	Continuing with the argument from Sub-Claim C4, and the Evidence E2 above, if the HA App Store states that it only verifies applications that references and communicates to devices via IP address this argument would be sound. As the devices are on a network and must be referenced by HA somehow to receive the automation commands, standardizing this method would greatly improve the security of HA.  

UM1: https://www.home-assistant.io/integrations/ambiclimate/
	This is a continuation of  the argument in Evidence E2, showing that some devices are only referenced by HA by a user defined “client_id”. While this gives the user more control over their devices, and likely was done to make the user experience more user friendly, this is a serious security flaw that could be exploited by a malicious user.


### Reflection
###### [Return to Top](#assurance-case-for-system-security-engineering)

Over the last few weeks, the group has certainly grown together, and we are working much more smoothly as a unit. We are all getting more comfortable with the subject matter and the way that the class is being taught. OSS is a new topic for all of us, and it seemed that there was trepidation from everyone about how this project was to be done, and what the expectations of the work were. After we received feedback on the first assignment, it was more clear what is expected of us. As such, we have been much better equipped to take on the project’s tasks. 

Communication between group members has been fantastic, and the sharing of knowledge that comes with that has been fantastic. As we all have knowledge gaps in one topic or another, the group has been able to assist each other in filling those gaps and helping each person move forward. We utilized the [Project Board](https://github.com/users/BigElkHunter/projects/1) to keep our tasks organized and developed a new [Comments Document](https://github.com/megharris/cyberockit/blob/main/images/Assurance%20Case%20Comments.md) to track our comments to each other and document our collaboration. This helped us to more effectively complete our project in a unified manner.

Going forward we will continue to draw on the strengths of the other members of the group to supplement our individual weaknesses. As this has been happening for the last few weeks, we are confident that we will continue to succeed in our assignments for the class. 
