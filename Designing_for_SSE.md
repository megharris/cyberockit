# Designing for Software Security Engineering

## Index
### SECTION ONE
* **[Add-ons](#model-1)**
* **[Authentication](#model-2)**
* **[IoT Devices](#model-3)**


### SECTION TWO
* **[Observations](#observations)**

### SECTION THREE
* **[Reflection](#reflection)**

## SECTION ONE
### Model 1
#### Add-ons
###### [Return to Top](#designing-for-software-security-engineering)
![threatmodel3](https://user-images.githubusercontent.com/63809979/141689141-8ae68360-dca5-4bb3-9bac-1a12d07e1be2.PNG)


### Model 2
#### Authentication
###### [Return to Top](#designing-for-software-security-engineering)
![threatmodel2](https://user-images.githubusercontent.com/63809979/141689146-7235f9bf-ec9d-4ed8-a522-39c36cf228d9.PNG)


### Model 3
#### IoT Devices
###### [Return to Top](#designing-for-software-security-engineering)
![threatmodel1](https://user-images.githubusercontent.com/63809979/141695329-0b2bca10-5870-4c4e-af3f-e1343ce47366.PNG)



## Observations
[Threat Modeling Report](DFD Assignment/)

### Add-ons 

Any process by [add-ons](https://developers.home-assistant.io/docs/add-ons/security/) are run in protection enabled mode which does not allow the process to have more previlege than they need to carry out their regular functions. HA also uses API roles from supervisor to use the supervisor store for installation of add-ons into the system. 

### Authentication
A couple of our models included some sort of user access that is dependent on authentication to access the Home Assistant interface. Home Assistant includes mitigations for these threats with the Authentication system [here](https://www.home-assistant.io/docs/authentication/). A number of threats that arose from the threat modeling tool were mitigated by establishing a logging or audit function. Home Assistant has the Logger integration which seems to address these issues available [here](https://www.home-assistant.io/integrations/logger/). Let's Encrypt also includes a logging system that records certificates issued. Your local Home Assistant can then see if the certificates are being impersonated.

### IoT Devices
The threats associated with accessing the cloud seem to be mitigated by NabuCasa. NabuCasa encrypts all data between your browser and your local Home Assistant Instance. Additionally, when logging in with NabuCasa authentication is done with your local credentials, but these credentials are stored locally and cannot be impersonated. More security docuentation on NabuCasa can be seen [here](https://www.nabucasa.com/config/remote/). The Let's Encrypt integration helps implement additional data encryption and works well with NabuCasa for cloud access.

### STRIDE References
#### Spoofing
Spoofing the user external entity and the user external destination entity in all three of our models, is mitigated in Home Assistant with basic and multi-factor authentication. Spoofing the IoT Device external destination entity is mitigated outside of Home Assistant for the device itself (usually in place but dependent on the device maker), and is dependent on Home Assistant's authentication for access through Home Assistant. Spoofing the core process is mitigated by the same basic authentication process as previously mentioned. Spoofing of the cloud data storage destination and source are mitigated by encrypting the data flow and providing authentication for access to the source and the cloud storage entity. Nabu Casa is the cloud storage service associated with Home Assistant and all data is encrypted and credentials are set up on that site.

#### Tampering
Data flow of credentials may be tampered with, but this is mitigated by lock out after failed attempts and proper authentication. Some evidence for failed log-in detection is available and Home Assistant does provide standard authentication. If the authentication doesn't provide access lock out after a number of failed attempts this may be worth looking into. 

#### Repudiation
Data repudiation by the Home Assistant core is mitigated by logging or auditing source, time and summary of the received data. It looks like the Logger integration available with Home Assistant provides configurable logging capabilities that seem to mitigate these threats. Data repudiation by installed applications would be mitigated by logging and auditing as described above and the Logger integration would mitigate this threat as well. External IoT devices denying receiving of data and cloud storage denying write data would also be mitigated by the Logger integration. 

#### Information Disclosure
Access control for the database resource should be mitigated by the standard authentication in Home Assistant. It looks like Home Assistant uses an internal SQLite database that would only be accessible through the main Home Assistant instance. Data flow sniffing would be mitigated by data encryption, in Home Assistant both Nabu Casa and the Let's Encrypt integration provide data encryption. Data flow sniffing of IoT device data flows would be mitigated by both the data encryption available on the IoT device, as well as the Let's Encrypt integration available with Home Assistant. Devices like EcoBee for example have inherent data encryption. Data flow sniffing across the cloud storage boundary is mitigated by encryption of the data flow to and from the cloud. Home Assistant provides the Let's Encrypt integration and the cloud service Nabu Casa provides advanced encryption which mitigates this threat. 

#### Denial of Service
Potential excess resource consumption attacks would be mitigated by timeouts and resource consumption controls. The system monitor platform monitors disk usage, memory, CPU, and running processes. 

#### Elevation of Privelege
Cross-site request forgery would apply here with the remote access. The threat to the user's browser can be mitigated in transit via TLS and SSL. The remote access integration with Home Assistant is done with Nabu Casa, wghich uses the Duck DNS add-on integration. Duck DNS uses the TLS/SSL so this threat is mitigated. Encryption with Let's Encrypt is also useful here to protect the data flow.

### Reflection
###### [Return to Top](#assurance-case-for-system-security-engineering)
