# Added Features

A range of **functional features** has been added to the CoD4x client. Some of which are described and explained in the following sections.

## Add Favorites to Serverbrowser

In the original game it was a big hassle to manage server favorites as it required manually typing the IP addresses and ports for servers. Especially, when the favorite list bugs out again and deletes itself \*sigh\*.

CoD4x adds the client command `addFavorite` to make management of your favorite servers more convenient. The command can be used in two ways.

* **You are currently playing on a server**  
  Just type `\addFavorite` into your console and the server you are playing on will be added to your favorites

* **In every other case ...**  
  ... you can just add the ip and port as an argument to the command, to add any server to your favorites.  
  E.g.: `\addFavorite 127.0.0.1:28960`

## Steam Groups
CoD4x makes playing with your clan tag more convenient. Make sure your steam client is running already, and start the game. Open up the console and start typing `\clan`. \(**Make sure you hit the spacebar after typing **`clan`\). The auto-completion will show to you your available steam groups. By typing `\clan <number>` you can select any of them. Typing `\clan 0` removes any currently shown steam group from your name.

## XAsset Limits
You are able to load more of some XAssets. Note that is quite untested.
XModels can exceed 1000 and this is tested up to 1050. Weaponlimit is still 128, however you can exceed this which results in undefined behaviour on Server/Client including crashing. (Not recommended)
Menu assets stays at 640.
Images and XAnims are not tried yet
To make use of higher limites you have to start your server with an additional commandline parameter. For example:
+set r_xassetnum "xmodel=1200 xanim=320

## Memorylimit raised
In some cases the stock game will give an error like: "Can not allocate more than 152Megabytes." This Limit is now increased and controlled by a cvar called com_hunkmegs. However it will not effect the client if you raise the limit on the server
In rare cases it could be possible the player's GUID is the Steam3ID of the player

## Playerauthentication via Hardware ID
Players will get authenticated based on their hardware ID, players GUIDs will be based on it.
However never use this GUIDs for admin authentication which gives advanced permissions to players. There already exists a bypass for it. If this exploit is getting used too much, Steam will have to become a requirement

## Measures towards cheats
Cheats are a big problem in any online game, and even more so in such an old game as CoD4
Cod4X has a few measures which should render most existing cheats unusable. For example norecoil will not work without some new energy from an evil minded programmer.
Screenshots can be requested via the "getss" command. However it seems to be buggy at the moment, and it kicks many players. Screenshots are stored in "fs_homepath/screenshots".
A new cvar is added: sv_screenshotArrivedCmd
This cvar will execute a program once the screenshot is there. Don't consider this as an anticheat, because it isn't one

## Admin commands
AdminRemoveAdmin: Removes an admin by their UID
AdminAddAdmin: Adds an admin by name (if the player is on the server) or UID
AdminListAdmins: Lists all existing admins
cmdlist: will give you a list of available commands for your current powerpoints. Traditional rcon has 100 powerpoints
AdminListCommands: same as cmdlist but also prints needed power. Does exclude commands requiring 100 powerpoints
AdminChangePassword: (usually not needed. Only used for login into HL2 compatible rcon)
AdminChangeCommandPower: Changes the required power needed to execute a command
ChangePassword: (usually not needed. Only for login into HL2 compatible rcon)
- All commands can be used from rcon or the console. Ingame you can invoke them by typing them into chat with a leading $-character. Example: $cmdlist
- All these commands require Steam. You will need rcon for the initial setup

## Spectating invisible
You can now spectate players and will not show up on the scoreboard. You have to use the "undercover" or $undercover command

## Long playernames
Did you think the 15 character limit was annoying? Now players can use up to 32 characters in their names

## Server-side scripts
Server-side scripts are now supported. Create a folder in the root of your Cod4 folder called "main_shared", and place any files in there, while keeping the regular file structure (so for example "maps/mp/gametypes"). Make sure the extensions are .gsx instead of .gsc to let them overwrite the default game files
