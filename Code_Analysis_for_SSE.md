Manual Code Review Points:

**Core**

https://github.com/home-assistant/core/tree/dev/homeassistant/auth
for authentication

https://github.com/home-assistant/core/tree/dev/homeassistant/components
we can look at a couple of internal component list and see how they interact with HA. Not Sure if required

https://github.com/home-assistant/core/tree/dev/homeassistant/util
for checking the different security measures while dealing with IO needs further review because all .py files are not required for review

https://github.com/home-assistant/core/blob/dev/homeassistant/config_entries.py
https://github.com/home-assistant/core/blob/dev/homeassistant/core.py

**Supervisor**

https://github.com/home-assistant/supervisor/tree/main/supervisor/addons
check: data, addons, init and validate


https://github.com/home-assistant/supervisor/tree/main/supervisor/hardware
check: data, helper, manager, monitor and policy

https://github.com/home-assistant/supervisor/tree/main/supervisor/homeassistant
check: api, core, module and websocket

https://github.com/home-assistant/supervisor/tree/main/supervisor/store
check: data.py

https://github.com/home-assistant/supervisor/tree/main/supervisor/utils
not sure but needs to be considered for future work

