A device which allows you to get player input using a keyboard-like interface.

## Table of contents

### Methods
* [`void Keyboard:SimulateKeyPress(string? key, string Player)`](#void-keyboardsimulatekeypressstring-key-string-player)
* [`void Keyboard:SimulateTextInput(string? input, string Player)`](#void-keyboardsimulatetextinputstring-input-string-player)

### Events
* [`Event Keyboard.KeyPressed(KeyCode key, string keyString, UserInputState state, string Player)
* [`Event Keyboard.TextInputted(string text, string Player)`](#event-keyboardtextinputtedstring-text-string-player)
___

## `void Keyboard:SimulateKeyPress(string? key, string Player)`

> Takes a string as a key to press and simulates pressing that key for the Keyboard.

___

## `void Keyboard:SimulateTextInput(string? input, string Player)`

> Takes a string as input and simulates typing that string for the Keyboard.

___

## `Event Keyboard.KeyPressed(KeyCode key, string keyString, UserInputState state, string Player)`

> An event which fires when a Player presses a key on the Keyboard.
`keyString` is the key pressed as a string (for example, `a` if the player pressed A.) If shift is held, the keyString will be capitalized. If the key is non-printable (i.e. shift or return) `keyString` will be nil.
`state` is always Enum.UserInputType.End.

___

## `Event Keyboard.TextInputted(string text, string Player)`

> An event which fires when a Player presses "Enter" on the keyboard.
