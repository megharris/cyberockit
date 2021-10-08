![Assurance Case Jay](https://github.com/megharris/cyberockit/blob/main/images/JayChavhanAssuranceCaseUpdatedV3.png)
Evidence for Assurance Case - Jay
<h4/> Evidence alignment <h4/> <br/>
E1: DuckDNS is introduced in HA 0.55 <br/> 
	<p/>Port-forwarding is one of the best way for remote access. HTTPS encryption is required for secured port-forwarding. DuckDNS provides HTTPS encryption and single URL to access HA remotely.<p/>

<https://www.home-assistant.io/integrations/duckdns/> <br/>
<https://github.com/home-assistant/core/tree/dev/homeassistant/components/duckdns> <br/>

E2: Configuration documentation for remote access providing SSH manual<br/>
	<p/> SSH provides more privacy and security. Using SSH/Terminal is beneficial to Undo the changes which were done by mistake.<p/>
<https://www.home-assistant.io/blog/2017/11/02/secure-shell-tunnel/> <br/>
<https://www.home-assistant.io/docs/configuration/securing/#remote-access> <br/>

E3: Configuration documentation for VPN <br/>
	<p/>Using VPN provides the encryption for the links between devices and network. Documentation provides the correct way to implement it. <p/>
<https://www.home-assistant.io/docs/configuration/securing/#remote-access> <br/>
For more infromation [click here](<https://pivpn.io/>)


E4: IP filtering and banning documentation explains the concept of IP address filtering and banning them when hacker tries to attempt different passwords for several times. <br/>

<https://www.home-assistant.io/integrations/http#ip-filtering-and-banning > <br/>

E5: For evidence 5 IP_bans.yaml shows the status of Ip ban (enabled/disabled). This should be set to enabled by default. Brute force attacks can be prevented by enabling Ip ban. Set Ip_ban_enabled to true and maximum number of attempts. After first ban, ip_ban.yaml file is created in configuration folder. Notification to HA is also sent.



![Assurance Case Meg](https://github.com/megharris/cyberockit/blob/main/images/Assurance%20Case%202.png)
Evidence for Assurance Case - Meg


![Assurance Case Noah](https://github.com/megharris/cyberockit/blob/main/images/NZ-assurance%20case.md)
Evidence for Assurance Case - Noah


![Assurance Case Shifat](https://github.com/megharris/cyberockit/blob/main/images/updated_Add_On_Assurance%20Case.png)
Evidence for Assurance Case - Shifat


![Assurance Case Dylan](https://github.com/megharris/cyberockit/blob/main/images/DylanAssuranceCaseV5.drawio.png)

Evidence for Assurance Case – Dylan
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

Reflection:
	Over the last few weeks, the group has certainly grown together, and we are working much more smoothly as a unit. I believe we are all getting more comfortable with the subject matter and the way that the class is being taught. OSS is a new topic for all of us, and it seemed that there was trepidation from everyone about how this project was to be done, and what the expectations of the work were. After the feedback on the first assignment clarified what we are needing to do and what is expected of us, we have been much better equipped to take on the project’s tasks. 
	Communication between group members has been fantastic, and the sharing of knowledge that comes with that has been fantastic. As we all have knowledge gaps in one topic or another, the group has been able to assist each other in filling those gaps and helping each person move forward. 
	Going forward we will continue to draw on the strengths of the other members of the group to supplement our individual weaknesses. As this has been happening for the last few weeks, I am confident that we will continue to succeed in our assignments for the class. 



Reflection:
	Over the last few weeks, the group has certainly grown together, and we are working much more smoothly as a unit. I believe we are all getting more comfortable with the subject matter and the way that the class is being taught. OSS is a new topic for all of us, and it seemed that there was trepidation from everyone about how this project was to be done, and what the expectations of the work were. After the feedback on the first assignment clarified what we are needing to do and what is expected of us, we have been much better equipped to take on the project’s tasks. 
	Communication between group members has been fantastic, and the sharing of knowledge that comes with that has been fantastic. As we all have knowledge gaps in one topic or another, the group has been able to assist each other in filling those gaps and helping each person move forward. 
	Going forward we will continue to draw on the strengths of the other members of the group to supplement our individual weaknesses. As this has been happening for the last few weeks, I am confident that we will continue to succeed in our assignments for the class. 
