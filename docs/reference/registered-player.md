# RegisteredPlayer

## Variables

### RegisteredPlayer.AccountAge

```lua
RegisteredPlayer.AccountAge: number

Account age of the RegisterPlayer
```

### RegisteredPlayer.DisplayName

```lua
RegisteredPlayer.DisplayName: string

Display name of the RegisterPlayer
```

### RegisteredPlayer.Username

```lua
RegisteredPlayer.Username: string

Username of the RegisterPlayer
```

### RegisteredPlayer.UserId

```lua
RegisteredPlayer.UserId: number

UserId of the RegisterPlayer
```

### RegisteredPlayer.PermissionLevel

```lua
RegisteredPlayer.PermissionLevel: number

Permission level of the RegisterPlayer
```

### RegisteredPlayer.Region

```lua
RegisteredPlayer.Region: string

Region of the RegisterPlayer
```

### RegisteredPlayer.PolicyInfo

```lua
RegisteredPlayer.PolicyInfo: {}

Policy information of the RegisterPlayer
```

### RegisteredPlayer.JoinTime

```lua
RegisteredPlayer.JoinTime: number

Join time of the RegisterPlayer
```

### RegisteredPlayer.Player

```lua
RegisteredPlayer.Player: Player

Player instance of the RegisterPlayer
```

### RegisteredPlayer.ExecutionLog

```lua
RegisteredPlayer.ExecutionLog: {}

Execution log of the RegisterPlayer
```

### RegisteredPlayer.GameHistory

```lua
RegisteredPlayer.GameHistory: {}

Game history of the RegisterPlayer
```

## Functions

### RegisteredPlayer:SetPermission()

```lua
RegisteredPlayer:SetPermission(PermissionLevel: number | nil) -> RegisterPlayer.PermissionLevel

Sets the RegisteredPlayer permission level
```

### RegisteredPlayer:LogExecution()

```lua
RegisteredPlayer:LogExecution(command: string,arguments: {}?,response: any) -> RegisterPlayer

Logs command execution for the RegisteredPlayer
```

### RegisteredPlayer:LogHistory()

```lua
RegisteredPlayer:LogHistory(player: Player,history: {any}?) -> RegisterPlayer

Logs game history for the RegisteredPlayer
```
