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

## javascript_placeholders.yml
If you have the javascript expansion enabled, the plugin will generate a javascript_placeholders.yml file where you can create your own placeholders.  
There are 2 ways you can create these javascript based placeholders. Either specify the javascript directly in the expression: section for each placeholder, or specify a file that the javascript will be loaded from by setting the expression to the following format:  
`expression: 'file: <filename with extension>'`

When an expression starts with the "file: " keyword, a file will be created in the /plugins/PlaceholderAPI/javascripts folder with the name and file format specified if it does not exist.

These placeholders are reloaded on /placeholderapi reload so no need to restart your server to make changes.  
```yaml
# javascript_placeholders.yml
# You can create custom placeholders which utilize javascript to determine the result of the custom placeholder you create.
# You can specify if the result is based on a boolean or the actual javascript.
#
# If you do not specify a type: the placeholder will default to a boolean type
# A boolean type must contain a true_result: and false_result:
#
# A string type only requires the expression: entry
#
# Javascript placeholders can contain normal placeholders in the expression, true_result, or false_result
# These placeholders will be parsed to the correct values before the expression is evaluated.
#
# Your javascript placeholders will be identified by: %javascript_<identifier>%
#
# Javascript placeholder format:
#
#     BOOLEAN TYPE
# <identifier>:
#   expression: <expression>
#   type: 'boolean'
#   true_result: <result if expression is true>
#   false_result: <result if expression is false>
#
#     STRING TYPE
# <identifier>:
#   expression: <expression>
#   type: 'string'
#
#
#  ==== ADVANCED VARIABLES ====
# DO NOT USE THESE VARIABLES UNLESS YOU KNOW WHAT YOU ARE DOING!
#
# You can access a few Bukkit API classes and methods using certain keywords:
#
# Using "BukkitServer" in your javascript will return Bukkit.getServer()
# You can use any methods inside of the Server class:
#
# Example: BukkitServer.getBannedPlayers().size().toFixed()
# Will return how many players are banned
#
# This variable is handy if you want to iterate through all online players.'
#
# Using "BukkitPlayer" in your javascript will return the Player object you are setting placeholders for.
# You can use any methods inside of the Player class:
#
# Example: BukkitPlayer.hasPermission("some.permission")
# Will return if the player has a specific permission
# This variable is handy if you want to check a players permission node, or access other methods inside of
# the player class for the specified player.
#
# More advanced variables are coming soon! Only use these variables if you know what you are doing!
#
#  ==================
#
#
# Javascript placeholder examples:
#
# millionaire:
#   expression: '%vaulteco_balance% >= 1000000'
#   type: 'boolean'
#   true_result: '&aMillionaire'
#   false_result: '&cbroke'
# is_staff:
#   expression: '"%vault_group%" == "Moderator" || "%vault_group%" == "Admin" || "%vault_group%" == "Owner"'
#   type: 'boolean'
#   true_result: '&bStaff'
#   false_result: '&ePlayer'
# health_rounded:
#   expression: 'Math.round(%player_health%)'
#   type: 'string'
# staff_online:
#   expression: 'var i = 0; for (var p in BukkitServer.getOnlinePlayers()) { if (BukkitServer.getOnlinePlayers()[p].hasPermission("staff.online")) {i = i+1;};} i.toFixed();'
#   type: 'string'
#
#
# You can optionally specify a file that the javascript expression will be loaded from if your expression
# is bigger than 1 line. To specify javascript be loaded from a file, follow this format:
#
# is_op:
#   expression: 'file: is_op.js'
#   type: 'string'
#
# The following placeholder will attempt to load javascript from the /plugins/PlaceholderAPI/javascripts/is_op.js file
# if the folder/file exists. If the folder/file does not exist it will be created.
# You must specify the file extension with the file name. Any file extension is accepted.

millionaire:
  expression: '%vaulteco_balance% >= 1000000'
  type: boolean
  true_result: '&aMillionaire'
  false_result: '&cbroke'
is_staff:
  expression: '"%vault_group%" == "Moderator" || "%vault_group%" == "Admin" || "%vault_group%"
    == "Owner"'
  type: boolean
  true_result: '&bStaff'
  false_result: '&ePlayer'
staff_online:
  type: string
```

![](https://www.spigotmc.org/attachments/permissions2-png.323868/)  
```yaml
permissions:
    placeholderapi.admin:
        description: ability to use admin commands
        default: op
```

![](https://www.spigotmc.org/attachments/commands2-png.323864/)  
![](https://img.extendedclip.com/javaw_2018-03-03_01-07-19.png)


![](https://www.spigotmc.org/attachments/api_usage2-png.323863/)  
You can find a tutorial on how to use PlaceholderAPI for your own plugin on the [wiki](https://github.com/help-chat/PlaceholderAPI/wiki/Hook-into-PlaceholderAPI)

## Statistics
This plugin utilizes bStats to collect anonymous statistics
https://bstats.org/plugin/bukkit/PlaceholderAPI
