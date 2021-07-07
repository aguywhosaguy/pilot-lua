A class which lets you create signals similar to Roblox instance signals like Part.Touched. Do not mistake with WOS's internal Signal class! This class comes with a nested SignalConnection class which you dont need to create, its just a backbone of the Signal class itself and should be ignored!

## Table of contents

### Methods
* [`Signal Signal.new()`](#signal-signalnew)
* [`void Signal:Fire(...)`](#void-signalfire)
* [`SignalConnection Signal:Connect(function handler)`](#signalconnection-signalconnectfunction-handler)
* [`... Signal:Wait()`](#-signalwait)
* [`void Signal:Destroy()`](#void-signaldestroy)
* [`void SignalConnection:Disconnect()`](#void-signalconnectiondisconnect)
___

## `Signal Signal.new()`

> Creates a new Signal object.
___

## `void Signal:Fire(...)`

> Fires the signal. All connected handlers will be run with the arguments that you've passed to this function.
___

## `SignalConnection Signal:Connect(function handler)`

> Connects a new handler to the Signal object. The handler function you passed will run every time the signal is fired.
___

## `... Signal:Wait()`

> Yields the current thread until the Signal object has been fired. Returns the same arguments that were passed when firing the Signal.
___

## `void Signal:Destroy()`

> Prepares the Signal object to be discarded of. After running this function, feel free to set the Signal object to nil.
___

## `void SignalConnection:Disconnect()`

> Disconnects a SignalConnection object from the Signal that it has been connected to. The handler function will not be called when firing the Signal afterwards. After running this functio, feel free to set the SignalConnection object to nil.
___

# Source code

```lua
-- ignore this class and dont use it, its made for use within the Signal class. dont forget to copy this too though!
local SignalConnection = {}
SignalConnection.ClassName = "SignalConnection"
SignalConnection.__index = SignalConnection

function SignalConnection.new(container, index, handler)
	return setmetatable({
		_container = container;
		_index = index;
		_handler = handler;
	}, SignalConnection)
end

function SignalConnection:Disconnect()
	if self._container then
		self._container[self._index] = nil
	end
end

-- beginning of the Signal class itself
local Signal = {}
Signal.ClassName = "Signal"
Signal.__index = Signal

function Signal.new()
	return setmetatable({
		_waits = {};
		_handlers = {};
	}, Signal)
end

function Signal:Fire(...)
	for i, v in ipairs(self._waits) do
		coroutine.resume(v, ...)
		table.remove(self._waits, i)
	end

	for i, v in pairs(self._handlers) do
		local thread = coroutine.create(v._handler)
		coroutine.resume(thread, ...)
	end
end

function Signal:Connect(handler)
	assert(type(handler) == "function", "Passed value is not a function")

	local index = #self._handlers + 1
	local connection = SignalConnection.new(self._handlers, index, handler)

	table.insert(self._handlers, index, connection)
	
	return connection
end

function Signal:Wait()
	table.insert(self._waits, coroutine.running())
	return coroutine.yield()
end

function Signal:Destroy()
	for i, v in ipairs(self._waits) do
		coroutine.resume(v)
		table.remove(self._waits, i)
	end

	for i, connection in pairs(self._handlers) do
		connection:Disconnect()
	end
end
```
# Examples
```lua
local onThreeSecondsWaited = Signal.new() -- creates the signal and gives it an appropriate variable name for the situation we'll use it for

--[[
the line below connects the passed function to the signal in a way where when the signal is fired, the function will also run. 
this also returns a SignalConnection object which you can save to a variable to disconnect the function from the signal. 
you can add as many connections to one signal as you want
]]

local signalConnection = onThreeSecondsWaited:Connect(function()
   -- do something hehe!
end)

wait(3)

onThreeSecondsWaited:Fire() -- fires the signal, causing the handler function we set earlier to run

signalConnection:Disconnect() -- disconnects the connection so that the handler function above will stop executing when the signal is fired
```