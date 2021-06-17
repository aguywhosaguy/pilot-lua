# Microcontroller Globals
Only Roblox globals and libraries confirmed to be listed are shown on this page. (Some may be missing if this documentation is not consistently updated. Feel free to message me or create an `Issue` if updates are needed, preferably if you have information about the changes/additions)

# Basics

## [`float, float wait(optional float time)`](https://developer.roblox.com/en-us/api-reference/lua-docs/Roblox-Globals) (See linked doc page)
> Waits for a given time (in seconds). You can't wait any shorter than two Roblox ticks which is about `1/30`th of a second (Usually called "Heartbeat" which is very similar to FPS< but its for the server).
> You can (roughly!) measure the TPS of the server like so: `2/wait()`
> It returns the time that `wait` waited for which isn't perfect (Measuring the time yourself is more accurate), and it returns the same value that `elapsedTime()` would return. `elapsedTime` is removed from microcontrollers so this is one way to access this however better time measurements exist.

___

## `void print(Variant...)` **TODO**
> Prints some output. In Waste of Space this likely has been overridden to display output to a screen or as a chat bubble. It likely does not do the same thing as it does in regular Roblox code.

___

## **DO NOT USE** [`void delay(optional float time, function callback)`](https://developer.roblox.com/en-us/api-reference/lua-docs/Roblox-Globals) (See linked doc page)
> **NOTE**: (Due to the following this function may also be removed or have its functionality replaced in the future) It is not recommended that you use this function due to its heavy performance cost, slow action, and its potential to effect WoS' game loop if you use it in bulk. (Remember that intentionally crashing servers can get you banned!) Instead, see the (coroutines)[#coroutine] library
> Similar to `spawn`. Waits for the input time, then calls your function. Due to its internal mechanisms its very slow, and, it can cause Roblox to throttle calls to itself and also many timer functions like `wait()`. This can slow down a lot of stuff.

___

## **DO NOT USE** [`void spawn(function callback)`](https://developer.roblox.com/en-us/api-reference/lua-docs/Roblox-Globals) (See linked doc page)
> **NOTE**: (Due to the following this function may also be removed or have its functionality replaced in the future) See `delay` above.
> This is like calling `delay` with `0` as the time. This means that it still takes two Roblox frames like `wait()` does.

___

# coroutine
A library designed for creating threads. Its not important to understand how threads work on the inside, but, its good to mention that threads are actually very smart.

They don't cost a lot because all Roblox basically does is change *where* it wants to run code inside of your thread, and then when its done or when it pauses or errors, Roblox goes back to wherever it needs to be. This means that threads can be used as a way to stitch pieces of code together, but, like they are named, they are also useful for making things that appear to run at once. 

___
## `thread coroutine.create(function body)`
> Creates a thread with your function and returns the thread. You can use `coroutine.resume` with this new thread.

### Code example
```lua
coroutine.resume(coroutine.create(function()
	wait(1)
	print("After") -- 1 second after before
end))
print("Before")
```

# debug