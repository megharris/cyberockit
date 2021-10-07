# Version 1
![Assurance Case-NZ](https://user-images.githubusercontent.com/63809979/136254563-6dbc4057-470d-45d3-9e8e-ceef6d361aeb.png)

# Version 2
![Assurance Case-Page-2 drawio](https://user-images.githubusercontent.com/63809979/136254674-d00375cb-2ac3-4e82-914e-6cd564b0a514.png)

# Version 3
I think I may remove the middle R5 subclaim
![assuranceCaseNZ_V3](https://user-images.githubusercontent.com/63809979/136419588-b99552e3-f18a-4a2b-bf58-4609601b0ce9.png)

# Version 4
![assuranceCaseNZ_V4](https://user-images.githubusercontent.com/63809979/136455787-499a11ec-7bd7-437e-8fbf-3b519638ba6d.png)

# Version 5
![assuranceCaseNZ_V5](https://user-images.githubusercontent.com/63809979/136470792-e6c4c125-b652-4b83-962c-c02f7500cb2b.png)

## Feedback


## Evidence for Assurance Case
Home assistant allows the user to connect and use IoT devices within their home or work. By editing the configuration.yaml file, the user can set automatic alerts, and threshold settings for things like temperature, that they want to keep within a certain range. Setting up this connection with the IoT devices can be done via the user interface or throught the aforementioned yaml file. An inference for this case is that a compatible device will connect to Home Assistant. This is undecut by cases where the device may be comppatible but it doesn't connect. Then sub-claim c7 asserts that the supported devices should reasonably connect, and issues with connection can be solved with [tutorials available](https://www.home-assistant.io/docs/configuration/devices, as seen in evidence 4). If a mis-user can somehow access the yaml file, held on the Home Assistant device, then they may be able to alter the settings and alerts that the user previously set, this can be seen in Rebuttal 1. In sub-claim C2, there is a reasonable assumption that only the user can alter alert and threshold settings within their own configuration settinsg and user interface. Rebuttal 3 then asserts that if the mis-user accessed the yaml files through the interface they could then change the yaml files. In sub-claim 4 we see that the Home Assistant interface is reasonably secure and this is evident by evidence 1 and 2, password access and multi-factor authentication respectively.

Rebuttal 2 presents that if the mis-user can connect to the device, they would potentially be able to directly alter the IoT device settings without an alert being sent to the owner. Then in sub-claim 3 it is asserted that Home Assistant adequately notifies if other entities try to connect to devices in use, or if the connection is lost. The first rebuttal to this, rebuttal 4, asserts that this could be untrue if the IoT devices can form multiple connections. The sub-claim following this is that the user would then be quickly notified if the device threshold settings changed. This would be untrue, in rebuttal 7, if the user didn't set up connection alerts. Following this in sub-claim 8 it states that the Home Assistant system alerts connection changes and loss to user devices. This is evident in evidence 5 and 6 with lost connection alerts, and automatic reconnects, as seen [here](https://community.home-assistant.io/t/simple-mobile-notification-when-device-becomes-unavailable/255239).

From sub-claim 3 the other rebuttal R6, asserts that notification may not occur if there is another Home Assistant instance nearby. This is followed by sub-claim 6 which states that Home Assistant will notify if another Home Assistant is on the premises. This is important because some users want to set up another instance of Home Assistant to track multiple locations or extend the range within one location. The evidence E3 for this is linked device notification when using multiple Home Assistants. This would be underminded if the Home Assistant does not communicate with the first. Thus in sub-claim 9, Home Assistants should reasonably communicate, and the evidence for this is in main and secondary configurations, of [multiple Home Assistants](https://community.home-assistant.io/t/master-ha-instance-with-multiple-slaves/109849/2).


# Stuff for part 2
Given the issues of mis-users trying to control user IoT devices, there is security enabled for some of the issues raised. Alert integrations can be included as seen [here](https://www.home-assistant.io/integrations/alert/). Alerts can be set up in various capacities to alert the Home Assistant owners to changes in the state of their location. Certain integrations have lost connection alerts and settings, that provide a reasonable process of alerting and then trying to reconnect to the IoT device. This can be seen in the Homematic integration for [lost connection](https://www.home-assistant.io/integrations/homematic/#detecting-lost-connections). Finally there is some documentation on multiple Home Assistant instances communicating via MQTT, as available in a question [here](https://community.home-assistant.io/t/two-ha-instances-how-to-communicate-between-them/30877). There remains some uncertainty whether or not a misuser could then use another Home Assistant instance to communicate with IoT devices, though this would depend on the mis-user being on premises. The conversation on multiple instances is available [here](https://github.com/home-assistant/architecture/issues/246).
