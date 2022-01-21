# Solar API

## Variables

### API._version

```lua
API._version: string

Latest Version of the Solar API
```

## Functions

### API:RegisterPlayer()

```lua
API:RegisterPlayer(Player: Player) -> RegisteredPlayer

Registers a player into the Solar API
```

### API:UnregisterPlayer()

```lua
API:UnregisterPlayer(Player: Player) -> boolean

Unregisters a player from the Solar API
```

### API:GetPlayers()

```lua
API:GetPlayers() -> {[number]: RegisteredPlayer?}

Returns table of all registered players
```

### API:GetPlayer()

```lua
API:GetPlayer(Player: Player | string) -> RegisteredPlayer | nil

Returns a RegisterPlayer
```

### API:AddHook()

```lua
API:AddHook(Name: string,Folder: Folder) -> BindableEvent

Creates a BindableEvent in the specified folder
```

### API:AddEvent()

```lua
API:AddEvent(Name: string,Folder: Folder) -> RemoteEvent

Creates a RemoteEvent in the specified folder
```

### API:CreateReturnObject()

```lua
API:CreateReturnObject(Success: boolean,... : string) -> ReturnObject

Creates a ReturnObject using the entered arguments
```

### API.CreateCommand()

```lua
API.CreateCommand() -> CommandObject

Creates new CommandObject
```

### API:GetCommands()

```lua
API:GetCommands() -> {[number]: CommandObject?}

Returns all registered commands
```

### API:GetCommand()

```lua
API:GetCommand(command: string) -> CommandObject

Returns the CommandObject of the command
```

### API:ExecuteCommand()

```lua
API:ExecuteCommand(Player: Player,Command: string,Arguments: {any}) -> ReturnObject | boolean

Executes the command
```

### API:Initialize()

```lua
API:Initialize(RegisterCommandsByDefault: boolean, SettingsModule: ModuleScript?) -> void

Initializes Solar & registers commands
```
