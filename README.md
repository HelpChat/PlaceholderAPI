![](https://www.spigotmc.org/attachments/logo2-png.323867/)  
PlaceholderAPI is a plugin/library that allows servers the use of placeholders from a wide range of your favorite plugins collectively.  
Essentials, Factions, LuckPerms, Vault, AutoSell, GriefPrevention, etc....  
You can display information from your favorite plugins in any plugin that supports PlaceholderAPI. See a full list of placeholders and supported plugins below.  
Through the use of the Expansion cloud, PAPI effectively and efficiently allows you to pick and choose which placeholders you want to install. The Expansion cloud allows you to receive new placeholders, updates to existing placeholder expansions, and much more directly from your server without updating the actual plugin.  
With over 100,000 downloads, PlaceholderAPI is a must have for a server of any type or scale.

Do you have a plugin that has messages you want to use placeholders in, but the plugin doesn't support PlaceholderAPI directly? No worries... If you have ProtocolLib installed on your server, you can download and install [PlaceholderInjector](https://www.spigotmc.org/resources/chatinjector.38327/) and placeholders will be available even in messages from the spigot.yml  

![](https://www.spigotmc.org/attachments/placeholders2-png.323869/)  
A list of available placeholders can be found [here](https://github.com/help-chat/PlaceholderAPI/wiki).

![](https://www.spigotmc.org/attachments/pluginsusing2-png.323870/)  
For a list of plugins, that hook into PlaceholderAPI, click [here](https://www.spigotmc.org/wiki/placeholderapi-compatible-plugins/).

![](https://www.spigotmc.org/attachments/configs2-png.323865/)  
## config.yml
The config.yml contains the core plugin customization settings as well as a section specifically for expansions that wish to add configurable options too. 

Any settings an expansion may allow you to change will be added to the config.yml when that specific expansion is loaded.  
```yaml
# PlaceholderAPI version 2.8.1
# Created by extended_clip

check_updates: true
cloud_enabled: true
auto_install_expansions: true
boolean:
  'true': 'yes'
  'false': 'no'
date_format: MM/dd/yy HH:mm:ss
expansions:
  pinger:
    offline: offline
    check_interval: 10
    online: online
  vault:
    formatting:
      thousands: k
      trillions: T
      quadrillions: Q
      billions: B
      millions: M
  bungee:
    check_interval: 30
  javascript:
    engine: javascript
```

![](https://www.spigotmc.org/attachments/permissions2-png.323868/)  
```yaml
permissions:
    placeholderapi.admin:
        description: ability to use admin commands
        default: op
```  
![](https://www.spigotmc.org/attachments/commands2-png.323864/)

COMMAND | DESCRIPTION
------- | -----------
/papi info [expansion] | View information for a specific expansion
/papi parse [args] | Parse a String with placeholders
/papi parserel [player one] [player two] [args] | Parse a String with relation placeholders
/papi reload | Reload the config settings
/papi disablecloud | Disable the expansion cloud
/papi ecloud | View information about the PlaceholderAPI expansion cloud
/papi ecloud status | View status of the PlaceholderAPI expansion cloud
/papi ecloud list [all/author] [page] | List all available expansions
/papi ecloud info [expansion] | View information about a specific expansion on the ecloud
/papi ecloud download [expansion] | Download a specific expansion from the ecloud 

![](https://www.spigotmc.org/attachments/api_usage2-png.323863/)  
You can find a tutorial on how to use PlaceholderAPI for your own plugin on the [wiki](https://github.com/help-chat/PlaceholderAPI/wiki/Hook-into-PlaceholderAPI)

## Statistics
This plugin utilizes bStats to collect anonymous statistics
https://bstats.org/plugin/bukkit/PlaceholderAPI
