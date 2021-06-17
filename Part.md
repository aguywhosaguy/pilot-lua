# Part

**This documentation is incomplete. Please contribute via [Issues](../issues)!** \
The base type for all objects.

## Table of contents

* [`string Part.ClassName`](#string-partclassname)
* [`void Part:Trigger()`](#void-parttrigger)
* [`void Part:Configure([<string>property=<any>value] properties)`](#void-partconfigurestringpropertyanyvalue-properties)
* [`void Part:ConnectToEvent(string eventName, function callback)`](#void-partconnecttoeventstring-eventname-function-callback)

___

## `string Part.ClassName`

> A string representing the type of the object, for example, `Port` or `Screen`.

___

## `void Part:Trigger()`

> Triggers the part

___

## `void Part:Configure([<string>property=<any>value] properties)`

> Updates the part's configuration options.

### Code example

The following code example sets a switch's SwitchValue to be on.

```lua
local switch = GetPartFromPort(1, "Switch") -- A Switch part
switch:Configure( { SwitchValue = true } ) -- Set it to be on
```

___

## `void? Part:ConnectToEvent(string eventName, function callback)`

> Connects to an event on a part. Some parts have special events.
