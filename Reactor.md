**This documentation is incomplete. Please contribute via [Issues](../issues)!** \
A structure which generates steam using water and heat from radiation.

## Table of contents

### Methods
* [`array Reactor:GetFuel()`](#array-reactorgetfuel)
* [`number Reactor:GetTemp()`](#number-reactorgettemp)
___

## `array Reactor:GetFuel()`

> Returns an array with four numeric values each representative of their fuel rod. The order is strict and goes from the first to the fourth fuel rod.

### Code example
The following code will trigger the uranium dispenser when the reactor is out of fuel, thus auto-refilling it.
```lua
local reactor = GetPartFromPort(1, "Reactor")
local uraniumDispenser = GetPartFromPort(2, "Dispenser")

while task.wait() do
 for _, fuelAmount in pairs(reactor:GetFuel()) do
  if fuelAmount == 0 then
   uraniumDispenser:Dispense()
   task.wait(1)
  end
 end
end
```
___

## `number Reactor:GetTemp()`

> Returns a numeric value representing the current temperature of the Reactor in Fahrenheit. 