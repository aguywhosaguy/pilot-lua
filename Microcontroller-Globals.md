Microcontroller-specific globals. These are the bridge from the code to the game.

## Table of contents

* [Getting parts](#getting-parts)
  * [`Part GetPartFromPort(int port, string partType)`](#part-getpartfromportint-port-string-parttype)
  * [`Part GetPartsFromPort(int port)`](#array-getpartsfromportint-port)
* [Ports](#ports)
  * [`Port GetPort(int port)`](#port-getportint-port)
  * [`void TriggerPort(int port)`](#void-triggerportint-port)
* [Miscellaneous](#miscellaneous)
  * [`void Beep(float pitch)`](#void-beepfloat-pitch)
  * [`any JSONDecode(string json)`](#any-jsondecodestring-json-only-available-in-unstable)
  * [`string JSONEncode(any data)`](#string-jsonencodeany-data-only-available-in-unstable)

___

## Getting parts

### `Part GetPartFromPort(int port, string partType)`

> Gets a part from the port number you specify and the part type. One port can be attached to multiple parts, and `partType` selects which one based on its type (e.g. `"Screen"`).
>
> The port number is a Configurable property on the Port part. This is how you can tell your microcontroller which port you want to use.

#### Code example

This example gets the Screen connected to port 1, then it clears it.
```lua
local myScreen = GetPartFromPort(1, "Screen") -- Gets a Screen from port 1
myScreen:ClearElements() -- Clears the Screen. See the docs for the "Screen" part
```

___

### `array GetPartsFromPort(int port, string partType)` **POTENTIALLY UNFINISHED**

> Gets an array of parts from the given port number.

#### Code example

This example gets all Switches connected to port 1 and toggles each to be active.
<sub>Provided by [mawesome4ever](/mawesome4ever) in [#1](../issues/1)</sub>
```lua
local switches = GetPartsFromPort(1, "Switch") -- Gets all parts on port 1 with the type "Switch"
for _, switch in ipairs(switches) do -- Loops over each switch in the list of switches
    switch:Configure( { SwitchValue = true } ) -- Sets all switches' SwitchValue options to be on, so each switch is made active
end
```

___

## Ports

### `Port GetPort(int port)`

> Returns the `Port` specified by the port number you input. This is the same port number from `GetPartsFromPort`.

___

### `void TriggerPort(int port)`

> Triggers a `Port` with the port number you input. This is the same port number from `GetPartsFromPort`.

___

## Miscellaneous

### `void Beep(float pitch)`

> Beeps with the given `pitch`. *\*\*Beep!\*\**

### `any JSONDecode(string json)` <sub>**[Only Available in Unstable]**</sub>

> Takes a `json` string and decodes it, giving you a complex piece of data.

### `string JSONEncode(any data)` <sub>**[Only Available in Unstable]**</sub>

> Encodes the `data` you give as JSON. This can be used to store complex data as a simple string. A ton of modern web services use JSON.
> JSON can only encode basic data, like numbers, strings, and tables. Anything else will just encode like `nil` does. That means that you cannot encode Instances, userdatas, functions, threads, etc.