# Configuration

When Quests is first run, configuration files will be created in the /plugins/Quests directory. If this is your first time using Quests, just make sure the settings in **config.yml** are to your liking. Don't worry about any of the other files or folders for the time being.

{% hint style="info" %}
**Pro-tip:** Opening a .yml file that contains non-English characters on an English computer may not display those characters correctly. In the case of Windows, this is because Windows in English uses the ANSI character set, while the preferred format is UTF-8. Unfortunately, Windows makes this difficult to change, so we recommend an editing program that supports UTF-8. [Notepad++](https://notepad-plus-plus.org/) is a free and popular choice.
{% endhint %}

### config.yml

This file contains all settings relating to how Quests should perform once loaded. As such, changes made to this file must be configured and saved _before_ the server is started.

> [Click here to view the default config.yml file.](https://github.com/PikaMug/Quests/blob/master/main/src/main/resources/config.yml)

| Key | Data Type | Description |
| :--- | :--- | :--- |
| accept-timeout | number | How long \(in seconds\) a player should be able to accept/deny a quest before the prompt cancels automatically. |
| allow-command-questing | true/false | Whether or not players are allowed to accept and manage quests via command \(e.g. /quests take SomeQuest\). |
| allow-command-quests-with-npcs | true/false | Whether players can accept/manage NPC quests via command \(e.g. /quests take SomeQuest\). |
| allow-pranks | true/false | Whether or not to permit clicking Portals with the Quests Journal. |
| allow-quitting | true/false | Whether or not to permit quitting of taken quests |
| ask-confirmation | true/false | Whether or not players must type Yes/No to accept/deny a quest. |
| console-logging | number | 0 = disabled, 1 = track editing, 2 = and start/quit quests, 3 = and rewards, 4 = and debug information. |
| disable-command-feedback | true/false | Whether or not to disable Minecraft's sendCommandFeedback gamerule at startup. |
| generate-files-on-join | true/false | Either generate a player data file when that player first joins the server or only when they first use Quests. |
| ignore-locked-quests | true/false | Ignore locked quests when checking if a player has a quest. |
| kill-delay | number | How long \(in seconds\) a player should have to wait after they kill a player for a quest before they can kill that player again. |
| language | string | Which file from the /lang/ folder will be used. For example, a value of "FR-fr" will result in "/lang/FR-fr/strings.yml" being loaded. |
| max-quests | number | Maximum number of quests a given player can have at any time. |
| npc-effects.enabled | true/false | Whether to enable particle effects. Note that the client must have particles enabled. |
| npc-effects.new-quest | string | The particle effect to be played for a new quest \(ex. note, enchant, crit, spell, portal\). |
| npc-effects.redo-quest | string | The particle effect to be played for a repeatable quest \(ex. note, enchant, crit, spell, portal\). |
| show-requirements | true/false | Allow players to see requirements in /quest \[quest\] |
| show-titles | true/false | Display titles to players when accepting/completing quests. |
| strict-player-movement | number | Seconds between advanced player movement tracking. |
| storage-data.address | string | The IP address for optional storage |
| storage-data.database | string | The table name for optional storage |
| storage-data.username | string | The login username for optional storage |
| storage-data.password | string | The login password for optional storage |
| storage-data.pool-settings.max-pool-size | number | Advanced HikariCP setting |
| storage-data.pool-settings.min-idle | number | Advanced HikariCP setting |
| storage-data.pool-settings.max-lifetime | number | Advanced HikariCP setting |
| storage-data.pool-settings.connection-timeout | number | Advanced HikariCP setting |
| storage-method.player-data | string | yaml = file storage, mysql = remote storage, custom = developer storage |
| top-limit | number | Maximum number of quests that can be displayed by /quests top \[number\] |
| translate-names | true/false | Translate item name to client's game language. |
| translate-subcommands | true/false | Translate subcommands to server's plugin language. |

### actions.yml

This file holds custom actions which execute certain tasks and effects. Except for the included examples, actions are created prior to use in a Quest. This is best accomplished with the _/quests actions_ command.

> [Click here to view the default actions.yml file.](https://github.com/PikaMug/Quests/blob/master/main/src/main/resources/actions.yml)

### conditions.yml

This file holds custom conditions which are checked during gameplay. Except for the included examples, conditions are created prior to use in a Quest. This is best accomplished with the _/quests conditions_ command.

> [Click here to view the default conditions.yml file.](https://github.com/PikaMug/Quests/blob/master/main/src/main/resources/conditions.yml)

### quests.yml

This file consists of every single quest available. Although this file can be edited manually, it is recommended to use the _/quests editor_ command. Regardless, changes will not appear on the server until a _/questadmin reload_ is input.

> [Click here to view the default quests.yml file.](https://github.com/PikaMug/Quests/blob/master/main/src/main/resources/quests.yml)

