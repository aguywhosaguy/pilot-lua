**This documentation is incomplete. Please contribute via [Issues](../issues)!** \
The base type for all objects.

## Table of contents

### Properties
* [`string Part.ClassName`](#string-partclassname)

### Methods
* [`Color3 Part:GetColor()`](#color3-partgetcolor)
* [`Vector3 Part:GetSize()`](#vector3-partgetsize)
* [`void Part:Trigger()`](#void-parttrigger)
* [`void Part:Configure(dictionary properties)`](#void-partconfiguredictionary-properties)
* [`void Part:Connect(string eventName, function callback)`](#void-partconnectstring-eventname-function-callback)

### Events
* [`Event Part.Triggered()`](#events-part-triggered)
* [`Event Part.Configured()`](#events-part-configured)

___

## `string Part.ClassName`

> A string representing the type of the object, for example, `Port` or `Screen`.

___

## `Color3 Part:GetColor()`<sup>[IN UNSTABLE]</sup>

> Gets the color of the part as a Color3.

___

## `Vector3 Part:GetSize()`<sup>[IN UNSTABLE]</sup>

> Gets the size of the part as a Vector3.

___

## `void Part:Trigger()`

> Triggers the part

___

## `void Part:Configure(dictionary properties)`

> Updates the part's configuration options.

### Code example

The following code example sets a switch's SwitchValue to be on.

```lua
local switch = GetPartFromPort(1, "Switch") -- A Switch part
switch:Configure( { SwitchValue = true } ) -- Set it to be on
```

___

## `void? Part:Connect(string eventName, function callback)`

> Connects to an event on a part. Some parts have special events.

## `Event Part.Triggered()`

> An event which fires when the part is triggered.

## `Event Part.Configured()`

> An event which fires when the part is configured.
