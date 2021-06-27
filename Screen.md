A part which can display GUI content on its surface

## Table of contents
* [`Vector2 Screen:GetDimensions()`](#vector2-screengetdimensions)
* [`void Screen:ClearElements(string className, [<string>property=<any>value] properties)`](#void-screenclearelementsstring-classnamenil-stringpropertyanyvalue-properties)
* [`ScreenObject Screen:CreateElement(string elementClass, [<string>property=<any>value] properties)`](#screenobject-screencreateelementstring-classname-stringpropertyanyvalue-properties)

___

## `Vector2 Screen:GetDimensions()`

> Gets the Screen's width and height as a [Vector2](https://developer.roblox.com/en-us/api-reference/datatype/Vector2).

___

## `void Screen:ClearElements(string className=nil, [<string>property=<any>value] properties)`

> Clears the elements on the screen. Optional a `className` can be passed to select only a specific type of object. (The effect of `properties` is currently unknown but likely selects objects with those properties)

___

## `ScreenObject Screen:CreateElement(string className, [<string>property=<any>value] properties)`

> Creates a [[ScreenObject]] with the given `className` and returns it after setting the given `properties` for the object.