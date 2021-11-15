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
A number of threats that arose from the threat modeling tool were mitigated by establishing a logging or audit function. Home Assistant has the Logger integration which seems to address these issues. A couple of our models included some sort of user access that is dependent on authentication to access the Home Assistant interface. The threats that arose here are (). Home Assistant includes mitigations for these threats with the Authentication system [here](https://www.home-assistant.io/docs/authentication/). The threats associated with accessing the cloud seem to be mitigated by NabuCasa. NabuCasa encrypts all data between your browser and your local Home Assistant Instance. Additionally, when logging in with NabuCasa authentication is done with your local credentials, but these credentials are stored locally and cannot be impersonated. More security docuentation on NabuCasa can be seen [here](https://www.nabucasa.com/config/remote/). The Let's Encrypt integration helps implement additional data encryption and works well with NabuCasa. Let's Encrypt includes a logging system that records certificates issued. Your local Home Assistant can then see if the certificates are being impersonated.

### Add-ons 

### Authentication

https://www.home-assistant.io/integrations/logger/

### IoT Devices
https://www.nabucasa.com/

### STRIDE References
#### Spoofing

#### Tampering

#### Repudiation

#### Information Disclosure

#### Denial of Service

#### Elevation of Privelege

### Reflection
###### [Return to Top](#assurance-case-for-system-security-engineering)
