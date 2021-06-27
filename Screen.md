A part which can display GUI content on its surface

## Table of contents
* [`Vector2 Screen:GetDimensions()`](#vector2-screengetdimensions)
* [`void Screen:ClearElements(string className, dictionary properties)`](#void-screenclearelementsstring-classnamenil-dictionary-properties)
* [`ScreenObject Screen:CreateElement(string elementClass, dictionary properties)`](#screenobject-screencreateelementstring-classname-dictionary-properties)

___

## `Vector2 Screen:GetDimensions()`

> Gets the Screen's width and height as a [Vector2](https://developer.roblox.com/en-us/api-reference/datatype/Vector2).

___

## `void Screen:ClearElements(string className=nil, dictionary properties)`

> Clears the elements on the screen. Optionally a `className` can be passed to select only a specific type of object. (The effect of `properties` is currently unknown)

___

## `ScreenObject Screen:CreateElement(string className, dictionary properties)`

> Creates a [[ScreenObject]] with the given `className` and returns it after setting the given `properties` for the object.