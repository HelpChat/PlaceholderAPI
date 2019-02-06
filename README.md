![](https://www.spigotmc.org/attachments/logo2-png.323867/)  

# Note
> The wiki has been moved to the original [PlaceholderAPI](https://github.com/PlaceholderAPI/PlaceholderAPI) repository!  
> Please make your issues about the wiki there instead of here. This wiki and repository will no longer be maintained and might 
be deleted/archived at a later date!

PlaceholderAPI is a plugin/library that allows servers the use of placeholders from a wide range of your favorite plugins collectively.  
Essentials, Factions, LuckPerms, Vault, AutoSell, GriefPrevention, etc....  
You can display information from your favorite plugins in any plugin that supports PlaceholderAPI. See a full list of placeholders and supported plugins below.  
Through the use of the Expansion cloud, PAPI effectively and efficiently allows you to pick and choose which placeholders you want to install. The Expansion cloud allows you to receive new placeholders, updates to existing placeholder expansions, and much more directly from your server without updating the actual plugin.  
With over 100,000 downloads, PlaceholderAPI is a must have for a server of any type or scale.

> Do you have a plugin that has messages you want to use placeholders in, but the plugin doesn't support PlaceholderAPI directly? No worries... If you have ProtocolLib installed on your server, you can download and install [ChatInjector](https://www.spigotmc.org/resources/38327/) and placeholders will be available even in messages from the spigot.yml  

![](https://www.spigotmc.org/attachments/placeholders2-png.323869/)  
A list of available placeholders can be found [here](https://github.com/help-chat/PlaceholderAPI/wiki/Placeholders).

![](https://www.spigotmc.org/attachments/pluginsusing2-png.323870/)  
For a list of plugins, that hook into PlaceholderAPI, click [here](https://github.com/help-chat/PlaceholderAPI/wiki/Plugins-using-PlaceholderAPI).

![](https://www.spigotmc.org/attachments/configs2-png.323865/)  
## config.yml
The config.yml contains the core plugin customization settings as well as a section specifically for expansions that wish to add configurable options too. 

Any settings an expansion may allow you to change will be added to the config.yml when that specific expansion is loaded.  
```yaml
# PlaceholderAPI
# Version: 2.9.2
# Created by: extended_clip
# Contributors: https://github.com/PlaceholderAPI/PlaceholderAPI/graphs/contributors
# Issues: https://github.com/PlaceholderAPI/PlaceholderAPI/issues
# Expansions: https://api.extendedclip.com/all/
# Wiki: https://github.com/PlaceholderAPI/PlaceholderAPI/wiki
# Discord: https://helpch.at/discord
# No placeholders are provided with this plugin by default.
# Download placeholders: /papi ecloud
check_updates: true
cloud_enabled: true
cloud_allow_unverified_expansions: false
boolean:
  'true': 'yes'
  'false': 'no'
date_format: MM/dd/yy HH:mm:ss

```

![](https://www.spigotmc.org/attachments/permissions2-png.323868/)  
* `placeholderapi.admin` -  Provides access to all commands from PlaceholderAPI.

![](https://www.spigotmc.org/attachments/commands2-png.323864/)

`[args]` are optional  
`<args>` are required.

### Normal commands
Command                                           | Description                                         |
------------------------------------------------- | --------------------------------------------------- |
`/papi`                                           | Main command. Shows info about PlaceholderAPI       |
`/papi list`                                      | Lists all installed expansions, that are active     |
`/papi info <expansion>`                          | Gives info about an installed expansion             |
`/papi parse <player/me> <args>`                  | Parses a String with placeholders                   |
`/papi bcparse <player/me> <args>`                | Parses a String with placeholders and broadcasts it |
`/papi parserel <player one> <player two> <args>` | Parses a String with relational placeholders        |
`/papi register <filename>`                       | Register an expansion by its filename               |
`/papi unregister <expansion>`                    | Unregister an expansion                             |
`/papi reload`                                    | Reloads the plugin                                  |
`/papi disablecloud`                              | Disables the connection to the ecloud               |

### Ecloud commands
Command                                           | Description                                                            |
------------------------------------------------- | ---------------------------------------------------------------------- |
`/papi ecloud`                                    | Shows the ecloud commands                                              |
`/papi ecloud status`                             | Shows the current status of the ecloud                                 |
`/papi ecloud list <all/author/installed> [args]` | Lists all expansions, those of an author, or those that are installed  |
`/papi ecloud info <expansion>`                   | Gives info about an expansion on the ecloud                            |
`/papi ecloud versioninfo <expansion> <version>`  | Gives info about an specific version of an expansion                   |
`/papi ecloud placeholders <expansion>`           | Lists all placeholders of an expansion                                 |
`/papi ecloud download <expansion> [version]`     | Downloads an expansion (optionally a specific version) from the ecloud |
`/papi ecloud refresh`                            | Refreshes the connection to the ecloud                                 |
`/papi ecloud clear`                              | Clear the cache of the ecloud                                          |

![](https://www.spigotmc.org/attachments/api_usage2-png.323863/)  
You can find a tutorial on how to use PlaceholderAPI for your own plugin on the [wiki](https://github.com/help-chat/PlaceholderAPI/wiki/Hook-into-PlaceholderAPI)

## Statistics
This plugin utilizes bStats to collect anonymous statistics
https://bstats.org/plugin/bukkit/PlaceholderAPI
