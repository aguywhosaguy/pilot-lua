**This documentation is incomplete. Please contribute via [Issues](../issues)!** \
A structure which generates steam using water and heat from radiation.

## Table of contents

### Methods
* [`array Reactor:GetFuel()`](#array-reactorgetfuel)
___

## `array Reactor:GetFuel()`

> Returns an array with four numeric values each representative of their fuel rod. The order is strict and goes from the first to the fourth fuel rod.

### Code example
The following code will trigger the uranium dispenser when the reactor is out of fuel, thus auto-refilling it.
```lua
local reactor = GetPartFromPort(1, "Reactor")
local uraniumDispenser = GetPartFromPort(2, "Dispenser")

while wait() do
 for _, fuelAmount in pairs(reactor:GetFuel()) do
  if fuelAmount == 0 then
   uraniumDispenser:Trigger()
   wait(1)
   uraniumDispenser:Trigger()
  end
 end
end
```