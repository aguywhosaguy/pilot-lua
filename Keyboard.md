A device which allows you to get player input using a keyboard-like interface.

## Table of contents

### Methods
* [`void Keyboard:SimulateKeyPress(string? key, string Player)`](#void-keyboardsimulatekeypressstring-key-string-player)
* [`void Keyboard:SimulateTextInput(string? input, string Player)`](#void-keyboardsimulatetextinputstring-input-string-player)

### Events
* [`Signal Keyboard.KeyPressed(KeyCode key, string Player)`](#signal-keyboardkeypressedkeycode-key-string-player)
* [`Signal Keyboard.TextInputted(String text, string Player)`](#signal-keyboardtextinputtedstring-text-string-player)
___

## `void Keyboard:SimulateKeyPress(string? key, string Player)`

> Takes a string as a key to press and simulates pressing that key for the Keyboard.

___

## `void Keyboard:SimulateTextInput(string? input, string Player)`

> Takes a string as input and simulates typing that string for the Keyboard.

___

## `Signal Keyboard.KeyPressed(KeyCode key, string Player)`

> A Signal which fires when a Player presses a key on the Keyboard.

___

## `Signal Keyboard.TextInputted(String text, string Player)`

> A Signal which fires when a Player presses "Enter" on the keyboard.
