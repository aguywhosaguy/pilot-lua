# Navigation

## Info

* [[Home]]
  * [[Additional Resources]]
* [[Globals]]
  * [[Microcontroller Globals]]
  * [[Roblox Globals]]

## Parts
* [[Part]]
  * [[string Part.ClassName|Part#string-partclassname]]
  * [[void Part:Trigger()|Part#void-parttrigger]]
  * [[void Part:Configure([\<string\>property=\<any\>value] properties)|Part#void-partconfigurestringpropertyanyvalue-properties]]
  * [[void Part:ConnectToEvent(string eventName, function callback)|Part#void-partconnecttoeventstring-eventname-function-callback]]
  * [[Keyboard]]
    * [[void Keyboard:SimulateKeyPress(string? key, string Player)|Keyboard#void-keyboardsimulatekeypressstring-key-string-player]]
    * [[void Keyboard:SimulateTextInput(string? input, string Player)|Keyboard#void-keyboardsimulatetextinputstring-input-string-player]]
  * [[LifeSensor]]
    * [[ [\<string\>playerName=\<Vector3\>]position LifeSensor:GetReading()|LifeSensor#stringplayernamevector3position-lifesensorgetreading]]
  * [[Instrument]]
    * [[number Instrument:GetReading(int typeId=nil)|Instrument#number-instrumentgetreadingint-typeidnil]]
  * [[EnergyShield]]
    * number EnergyShield:GetShieldHealth()
  * [[Disk]]
    * void Disk:ClearDisk()
    * void Disk:Write(string key, string data)
    * string Disk:Read(string key)
  * [[Modem]]
    * void Modem:PostRequest(string domain, string data) - NOTE: NOT HTTP
    * string Modem:GetRequest(string domain) - NOTE: NOT HTTP
    * void Modem:SendMessage(string data, int id) - Sends a message (Like `MessagingService`) and has an event on the Modem (need to find event name, I believe its OnMessage)
  * [[Screen]]
    * [[TouchScreen]]
      * Cursor TouchScreen:GetCursor()
      * Cursor TouchScreen:GetCursors()
    * Vector2 Screen:GetDimensions()
    * void Screen:ClearElements(string className, [\<string\>property=\<any\>value] properties)
    * ScreenObject Screen:CreateElement(string elementClass, [\<string\>property=\<any\>value] properties)
  * [[Rail]]
    * void SetPosition(int depth)
  * [[StarMap]]
    * [Body? body] StarMap:GetBodies()
    * [System? system] StarMap:GetSystems()
  * [[Telescope]]
    * Coordinate? GetCoordinate(int x1, int y1, int x2, int y2)
  * [[Speaker]]
    * void Speaker:PlaySound(int soundId)
    * void Speaker:ClearSounds()
    * void Speaker:Chat(string message)
  * [[Microcontroller]]
    * void? Microcontroller:Communicate(any data)
## Additional objects
* [[ScreenObject]]
  * void ScreenObject:ChangeProperties([\<string\>property=\<any\>value] properties)
* [[Cursor]]
  * int Cursor.X
  * int Cursor.Y
  * string Cursor.Player
  * boolean Cursor.Pressed
* [[Coordinate]]
