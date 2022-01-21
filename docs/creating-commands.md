# Creating Commands

This tutorial will explain how you can start creating your own commands for Solar

It is fairly easy to do if you have knowledge of programming on Roblox (it is recommended you have a bit of experience with Roblox programming before continuing)

You should have Solar setup before starting this as it'll make it a lot easier :wink:

## Getting Started

We'll start by creating a new module script in the `Commands` folder (you can also use the `example.command` module script!)

The module script **must** end in `.command` or it will not register. You can set the name of your module script to anything you'd like (although it's good to have it named the same as your command name)[^1]

[^1]: The name of the module script does not change the name of your command, you can change the name of the command within the module script

Once you've created your module script, copy & paste the code below into it

```lua
local API = require(game:GetService("ReplicatedStorage"):WaitForChild("Solar"):WaitForChild("API"))

local Command = API.CreateCommand()
:SetName("example") --// Name of your command
:SetDescription("This is an example command") --// Description of your command
:SetPermissionLevel(4) --// Permission level of your command
:AddArgument("arg1","string",true) --// Command Argument (name,type,required)
:AddArgument("arg2","player",false) --// Command Argument 2 (name,type,required)
:SetOptions({ --// Command Options
	ParseArguments = true, --// Should arguments be parsed to their correct types or should they be sent as strings
	HideExecutionOnClient = false, --// Should command execution be hidden on the client?
	YieldOnClient = false, --// Should the client wait for this command to execute before closing
})
:SetMetadata({ --// Command Metadata
	LastCompatibleVersion = "0.3.1", --// Which version of Solar is this command compatible with
	ForceCompatibility = false, --// Should the module display an error when this command is outdated
})


Command:SetExecuteFunction(function(Player: API.RegisteredPlayer,arg1: string,arg2: {[number]: API.RegisteredPlayer}) --// Function to run when this command is executed
	print("Command executed, arguments: ",Player,arg1,arg2)
	return API:CreateReturnObject(true,"Hello from this command!")
end)

Command:SetHook("onRegister",function(Command)  --// Function which runs when this hook has been fired (hook name, callback)
	print("example has been registered!")
end)

return Command
```

You can configure the command using the command functions which are pretty self explanatory

## Execute Function

All commands **must** have an execution function or else they can not be executed. To add an execute function, type `Command:SetExecuteFunction(function() end)`

Below is an example execute function:

```lua
Command:SetExecuteFunction(function(Player: API.RegisteredPlayer,arg1: string,arg2: {[number]: API.RegisteredPlayer}) --// Function to run when this command is executed
	print("Command executed, arguments: ",Player,arg1,arg2)
	return API:CreateReturnObject(true,"Hello from this command!")
end)
```

The 1st argument of the `Command:SetExecuteFunction()` function is the callback, this is the function which is called when the command is executed.

When called, the 1st argument given will be a `RegisteredPlayer`, which is the user who executed the command.

Following that, the rest of the arguments will be the arguments entered by the player who executed the command.

You can do what you wish with the arguments. In the example command, it will print the command arguments to the console and then return a `ReturnObject`

Your command **must** return a return object if the `CommandObject.HideExecutionOnClient` is set to `false`.

If you do have the `CommandObject.HideExecutionOnClient` value set to `true` then you still need to return something but it will not be displayed to the client.

The return object is used to display an output message to the player who executed the command.

You can create a return object by calling `API:CreateReturnObject()`.
The arguments for this should be a table containing a success value and an output message

Example:

```lua
return API:CreateReturnObject(true,"Hello from this command!","you can also do multiple output messages by adding another argument")
```

Once you've done that, you can test your command!
Join your game, open the command bar and type in your command!

## Command Metadata

Command Metadata is useful for plugins & the API, you can add data which helps plugins and you can change the version of Solar which your command works on

You can add metadata by calling the `CommandObject:SetMetadata({})` function and change the values, example:

```lua
Command:SetMetadata({ 
    LastCompatibleVersion = "0.3.1", 
    ForceCompatibility = false,
})
```

You can access can view a commands metadata by typing `Command.Metadata`

## Command Hooks

Command Hooks are useful for executing code when the command is registered, before it is executed and after it is executed, below is a list of all hooks:

- `onRegister`
- `beforeExecute`
- `afterExecute`

You can register hooks by using the `CommandObject:SetHook()` function

Below is some example code for the `onRegister` hook

```lua
Command:SetHook("onRegister",function(Command)  --// Function which runs when this hook has been fired (hook name, callback)
	print("example has been registered!")
end)
```

It will print "example has been registed!" when the command is registered by the API.

The `CommandObject:SetHook()` function accepts two arguments, `HookName` and `Callback`

The `HookName` argument can be set to one of the three hooks or you can add your own

The `Callback` argument needs to be set to a function which is called when the hook is fired
