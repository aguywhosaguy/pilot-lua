# Microcontroller Globals
* [Part GetPartFromPort(int port, string partType)](#user-content-part-getpartfromportint-port-string-parttype)
* [Part GetPartsFromPort(int port)](#user-content-array-getpartsfromportint-port)

___

## `Part GetPartFromPort(int port, string partType)`
> Gets a part from the port number you specify and the part type. One port can be attached to multiple parts, and `partType` selects which one based on its type (e.g. `"Screen"`).
>
> The port number is a Configurable property on the Port part. This is how you can tell your microcontroller which port you want to use.

### Code example
```lua
local myScreen = GetPartFromPort(1, "Screen") -- Gets a Screen from port 1
myScreen:ClearElements() -- Clears the Screen. See the docs for the "Screen" part
```

___

## `Port GetPort(int port)`
> Returns the `Port` specified by the port number you input. This is the same port number from `GetPartsFromPort`.

___

## `void TriggerPort(int port)`
> Triggers a `Port` with the port number you input. This is the same port number from `GetPartsFromPort`.

___

## `array GetPartsFromPort(int port)`
**TODO**