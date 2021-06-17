# Microcontroller Globals

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

___

## Getting parts

### `Part GetPartFromPort(int port, string partType)`

> Gets a part from the port number you specify and the part type. One port can be attached to multiple parts, and `partType` selects which one based on its type (e.g. `"Screen"`).
>
> The port number is a Configurable property on the Port part. This is how you can tell your microcontroller which port you want to use.

#### Code example

```lua
local myScreen = GetPartFromPort(1, "Screen") -- Gets a Screen from port 1
myScreen:ClearElements() -- Clears the Screen. See the docs for the "Screen" part
```

___

### `array GetPartsFromPort(int port)` **POTENTIALLY UNFINISHED**

> Gets an array of parts from the given port number.

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