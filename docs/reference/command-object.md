# CommandObject

## Variables

### CommandObject.Name

```lua
CommandObject.Name: string

Name of the command
```

### CommandObject.Description

```lua
CommandObject.Description: string

Description of the command
```

### CommandObject.PermissionLevel

```lua
CommandObject.PermissionLevel: number

Permission level of the command
```

### CommandObject.Arguments

```lua
CommandObject.Arguments: {}

Table of command arguments
```

### CommandObject.Options

```lua
CommandObject.Options: {}

Options of the command
```

### CommandObject.Metadata

```lua
CommandObject.Metadata: {}

Metadata of the command
```

### CommandObject.Functions

```lua
CommandObject.Functions: {}

Command functions
```

### CommandObject.Hooks

```lua
CommandObject.Hooks: {}

Command hooks
```

## Functions

### CommandObject:SetName()

```lua
CommandObject:SetName(Name: string) -> CommandObject

Sets the name of the CommandObject
```

### CommandObject:SetDescription()

```lua
CommandObject:SetDescription(Description: string) -> CommandObject

Sets the description of the CommandObject
```

### CommandObject:SetPermissionLevel()

```lua
CommandObject:SetPermissionLevel(PermissionLevel: number) -> CommandObject

Sets the permission level of the CommandObject
```

### CommandObject:SetOptions()

```lua
CommandObject:SetOptions(Options: {}) -> CommandObject

Sets the options of the CommandObject
```

### CommandObject:SetMetadata()

```lua
CommandObject:SetMetadata(Metadata: {}) -> CommandObject

Sets the metadata of the CommandObject
```

### CommandObject:SetExecuteFunction()

```lua
CommandObject:SetExecuteFunction(Callback: (Player: Player,...any) -> ReturnObject?) -> CommandObject

Sets the execute callback of the CommandObject
```

### CommandObject:SetHook()

```lua
CommandObject:SetHook(HookName: string,callback: (...any) -> any) -> CommandObject

Sets the specific hook to the callback
```
