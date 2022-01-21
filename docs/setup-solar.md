# Setting Up Solar

Setting up Solar is fairly easy, follow the steps below to set it up and start using Solar!

## Initialization

Before Solar can work, you must initialize it using our API, this can be done by inserting a script into `ServerScriptService` with the code below:

```lua
local Solar = game:GetService("ReplicatedStorage"):WaitForChild("Solar")
local API = require(Solar:WaitForChild("API")) --// Require Solar API

--// Initialize Solar & register commands
API:Initialize()

```

Once you have done this, Solar should be up & running!

## Settings

Now it's time to configure Solar's settings. md-typeset

Open the `Settings` module located in the Solar folder

Once you've opened it, you can configure Solar.

### Command Bar Hotkeys

The 1st value (`Settings.CommandBarHotkeys`) is used to configure the keys used to open the command bar. The default key is `'`

To change the hotkey, replace the value with a [`KeyCode`](https://developer.roblox.com/en-us/api-reference/enum/KeyCode)

You can add multiple hotkeys, just add another value to the table, separated by a comma.

### Limit Command Bar Access

You can limit the command bar to users who have a permission level above 2

Change the `Settings.IsCommandBarRestricted` value to `true` or `false` to toggle it on/off

### Register Command Descendants

This is used to choose if you'd like to register the descendants of the commands folder (it is recommended you keep this on to make using command packs easier)

Change the `Settings.RegisterCommandDescendants` value to `true` to enable it or `false` to disable it

### Log API Errors & Info

This setting will make the API log errors and information about commands, command execution and more.

To log API errors, set the `Settings.LogAPIErrors` value to `true` (or `false` to disable it)
To log API information, set the `Settings.LogAPIInfo` value to `true` (or `false` to disable it)

### Data Saving

Solar will save data such as Player Permission Level (if it was changed in-game), Game History (history that commands can log to (for bans, kicks, etc)) and Execution Log.

You can configure which ones of these should be saved as well as the Data Store Key

```lua
DataStoreKey = "DefaultDataStoreKey", --// You should replace this to something random!
SavedData = { --// Data which is saved when player leaves game
    PermissionLevel = true, --// Should a players permission level be saved?
    GameHistory = true, --// Should a players history be saved? (recommended)
    ExecutionLog = false, --// Should a players command execution history be saved?
},
```

### Permissions

Configuring Permissions for Solar is one of the most important parts of the configuration.

In Solar, there are 3 ways you can give a user permissions,

- UserId & Username
- Group/Group Rank
- Asset/Gamepass

Solar also has 4[^1] permission levels:

[^1]: Additional permission levels can be added if needed

| Permission Level | Name  |
| ---------------- | ----- |
| `Level 1` | Player             |
| `Level 2` | Moderator          |
| `Level 3` | Administrator      |
| `Level 4` | Head Administrator |

When setting a users permission level, you only need to use the number

#### Player Permissions

To give a specific player permissions, paste the code below into the `Players` table in the `Settings.Permissions` table

```lua
[00000000] = { --// The UserId or Username of the player (UserId is recommended)
   Level = 4, --// The permission level of the player
},
```

The Index of this table (`00000000`) is the players UserId or Username. You should replace it with your own.

The `Level` value is the permission level, you can set it to any value between 1-4 depending on how much permission you'd like to give the player (scroll up to see each permission level)

You can duplicate the code and edit it to add more players.

#### Group Permissions

Group Permissions are a bit more advanced than player permissions. Paste the code below into the `Groups` table in the `Permissions` table

```lua
[00000000] = { --// The Group Id
   Level = 1, --// The permission level for the entire group
   Ranks = { --// The levels for each group rank
      [255] = { --// The ID of the group rank
         Level = 3, --// The permission level for the role
         Operator = "==", --// The relational operator for this role (read the docs for more information)
      },
   },
},
```

The Index of this table (`00000000`) is the ID of the group.

Inside the table, you can set a permission level for the whole group by changing the `Level` value to the permission level you'd like

You can also give certain ranks a permission level so all players who have that rank will get the permission level

To do this, edit or duplicate the 1st table in the `Ranks` table

```lua
[255] = { --// The ID of the group rank
    Level = 3, --// The permission level for the role
    Operator = "==", --// The relational operator for this role (read the docs for more information)
},
```

Set the Index of the table to the rank number of your role

Next, set the `Level` value to the permission level you'd like the role to receive

And after that, you can change the `Operator` value to one of the values below depending on how you'd like it to work

| Operator | Action  |
| ---------------- | ----- |
| `==` | Gives members of this role the permission level             |
| `>=` | Gives members of this role and members above this role the permisson level          |
| `<=` | Gives members of this role and members below this role the permission level      |
| `~=` | Gives anyone who is not a member of this role the permission level |
| `>`  | Gives members above this role the permission level |
| `<`  | Gives members below this role the permission level

You can repeat this process for the ranks you'd like to give permission levels to!

#### Asset Permissions

Asset permissions are useful if you have gamepasses to give permission levels. Paste the code below into the `Assets` table in the `Permissions` table

```lua
[00000000] = { --// The asset's ID
   Level = 3, --// The permission level for the players who own the asset
   Type = "gamepass", --// The value type (if you entered a gamepass's ID, type 'gamepass', otherwise type 'asset')
},
```

Set the Index (`00000000`) of the table to your gamepass or asset ID

Next, you can set the permission level you'd like owners of this asset to receive by changing the `Level` value

Finally, you should change the type to either `gamepass` or `asset` depending on the type of asset you entered (all assets other than gamepasses = `asset`)

### Changing Folder Locations

If you'd like to move where the `Commands`, `Plugins` and `Themes` folders are located, you need to update it within the settings

Change the `CommandsFolder` value to the folder of your commands if you moved the folder
Change the `PluginsFolder` value to the folder of your plugins if you moved the folder
Change the `ThemesFolder` value to the folder of your themes if you moved the folder
