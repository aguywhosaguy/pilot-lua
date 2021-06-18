Roblox globals and libraries accessible to microcontrollers.

## Table of contents

* [Basics](#basics)
  * [`number, number wait(float time=1/30)`](#number,number-waitfloat-time130)
  * [`tick`](#number-tick)
  * [`void print(any...)`](#void-printany-todo)
* [coroutine](#coroutine)
  * [`thread coroutine.create(function body)`](#thread-coroutinecreatefunction-body)
  * [`any... coroutine.resume(thread target, any...)`](#any-coroutineresumethread-target-any)
  * [`any... coroutine.yield(any...)`](#any-coroutineyieldany)
  * [`string coroutine.status(thread target)`](#string-coroutinestatusthread-target)
* [debug](#debug)
  * [`string debug.traceback(string prefix=nil, int level=1)`](#string-debugtracebackstring-prefixnil-int-level1)
* [Functions to avoid](#functions-to-avoid)


## Basics

### [`number, number wait(float time=1/30)`](https://developer.roblox.com/en-us/api-reference/lua-docs/Roblox-Globals)

> Waits for a given time (in seconds). You can't wait any shorter than two Roblox ticks which is about `1/30`th of a second (Usually called "Heartbeat" which is very similar to FPS, but its not frames being rendered, its physics and other stuff like sending data. A better way to write it would be TPS).
> It returns the time that `wait` waited for which isn't perfect (Measuring the time yourself is more accurate), and it returns the same value that `elapsedTime()` would return. `elapsedTime` is removed from microcontrollers so this is one way to access this however better time measurements exist.
> You can estimate the TPS of the server like so: `2/wait()`. This basically says "how many times wait would get called to take two seconds?" The time wait takes is roughly `2 * 1/TPS` because the time a tick takes is roughly `1/TPS`, so times two ticks for the wait time. You can simplify this to "wait takes roughly `2/TPS`" so to estimate `TPS` you can just do `2/wait()`.

___

### `number tick()`

> Returns the current time on the server in seconds.

___

### `void print(any...)` **TODO**

> Prints some output. In Waste of Space this likely has been overridden to display output to a screen or as a chat bubble. It likely does not do the same thing as it does in regular Roblox code.

___

## [`coroutine`](https://developer.roblox.com/en-us/api-reference/lua-docs/coroutine)

A library designed for creating threads. Its not important to understand how threads work on the inside, but, its good to mention that threads are actually very smart.

They don't cost a lot because all Roblox basically does is change *where* it wants to run code inside of your thread, and then when its done or when it pauses or errors, Roblox goes back to wherever it needs to be. This means that threads can be used as a way to stitch pieces of code together, but, like they are named, they are also useful for making things that appear to run at once.

___

### [`thread coroutine.create(function body)`](https://developer.roblox.com/en-us/api-reference/lua-docs/coroutine#coroutine-functions)

> Creates a thread with your function and returns the thread. You can use `coroutine.resume` with this new thread.

#### Code example for `coroutine.create`

```lua
-- Spawn a new thread
coroutine.resume(coroutine.create(function()
    wait(1) -- Start waiting for a second, this lets our print below run
    print("After") -- Prints 1 second after before
end))
print("Before") -- Prints before
```

___

### [`any... coroutine.resume(thread target, any...)`](https://developer.roblox.com/en-us/api-reference/lua-docs/coroutine#coroutine-functions)

> Resumes the given thread, `target`. Also passes in any arguments you place after, and returns any stuff the thread returned or yielded with.

___

### [`any... coroutine.yield(any...)`](https://developer.roblox.com/en-us/api-reference/lua-docs/coroutine#coroutine-functions)

> Works similar to `coroutine.resume`. Yields (pauses) the current thread, giving your arguments to the resumer thread, the thread that resumed the one calling yield. Once your thread gets resumed again by Roblox, it returns any arguments the new resumer passed.

___

### [`string coroutine.status(thread target)`](https://developer.roblox.com/en-us/api-reference/lua-docs/coroutine#coroutine-functions)

> Gets a status string for the thread.

## [`debug`](https://developer.roblox.com/en-us/api-reference/lua-docs/debug)

### [`string debug.traceback(string prefix=nil, int level=1)`](https://developer.roblox.com/en-us/api-reference/lua-docs/debug)

> Creates a stack trace based on a prefix to place before, and a `level` to get the stack from. For example, level `2` will get the stack trace relative to one function above. You can also use `0` to get the stack at the very root of the script.
> This is useful for creating debug output.

#### Code example for `debug.traceback`

This is a "fancy" way to pcall which puts the stack trace of the error after its message. It uses xpcall to set the error handler to `debug.traceback`.

To give a brief explanation, xpcall is just like pcall but it allows you to pass in an error handler function. This function gets called *at* the location of the error, and, whatever it returns gets returned as xpcall's second option (if `success` is false).

So, when an error message occurs, it returns `debug.traceback(errorMessage)` getting called where the error is, so, it gets the stack trace of the location of the error, and that means that what you will get is the error message but with a stack trace attached.

```lua
local success, errMessage = xpcall(myFunction, debug.traceback)
```

___

## Functions to avoid

### **DO NOT USE** [`void delay(optional float time, function callback)`](https://developer.roblox.com/en-us/api-reference/lua-docs/Roblox-Globals#functions)

> **NOTE**: (Due to the following this function may also be removed or have its functionality replaced in the future) It is not recommended that you use this function due to its heavy performance cost, slow action, and its potential to effect WoS' game loop if you use it in bulk. (Remember that intentionally crashing servers can get you banned!) Instead, see the (coroutines)[#coroutine] library
> Similar to `spawn`. Waits for the input time, then calls your function. Due to its internal mechanisms its very slow, and, it can cause Roblox to throttle calls to itself and also many timer functions like `wait()`. This can slow down a lot of stuff.

___

### **DO NOT USE** [`void spawn(function callback)`](https://developer.roblox.com/en-us/api-reference/lua-docs/Roblox-Globals#functions)

> **NOTE**: (Due to the following this function may also be removed or have its functionality replaced in the future) See `delay` above.
> This is like calling `delay` with `0` as the time. This means that it still takes two Roblox frames like `wait()` does.
