## TODO LIST

* [x] Document most significant Roblox globals
* [x] Document known Microcontroller globals
* [ ] Document additional globals
* [ ] Document all Parts' microcontroller entries (In detail)
* [ ] Add code examples for microcontroller entries
* [ ] Document all Parts' configurables (In detail)
* [ ] Document certain game mechanics related to microcontrollers such as Ethernet Cable and Ports
* [ ] Further documentation
* [ ] Organize documentation pages & clean up

## Parts (To be documented)

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
    * **DOCUMENT ME** number EnergyShield:GetShieldHealth()
  * [[Disk]]
    * **DOCUMENT ME** void Disk:ClearDisk()
    * **DOCUMENT ME** void Disk:Write(string key, string data)
    * **DOCUMENT ME** string Disk:Read(string key)
  * [[Modem]]
    * **DOCUMENT ME** void Modem:PostRequest(string domain, string data) - NOTE: NOT HTTP
    * **DOCUMENT ME** string Modem:GetRequest(string domain) - NOTE: NOT HTTP
    * **DOCUMENT ME** void Modem:SendMessage(string data, int id) - Sends a message (Like `MessagingService`) and has an event on the Modem (need to find event name, I believe its OnMessage)
  * [[Screen]]
    * **DOCUMENT ME** Vector2 Screen:GetDimensions()
    * **DOCUMENT ME** void Screen:ClearElements(string className, [\<string\>property=\<any\>value] properties)
    * **DOCUMENT ME** ScreenObject Screen:CreateElement(string elementClass, [\<string\>property=\<any\>value] properties)
    * [[TouchScreen]]
      * **DOCUMENT ME** Cursor TouchScreen:GetCursor()
      * **DOCUMENT ME** Cursor TouchScreen:GetCursors()
  * [[Rail]]
    * **DOCUMENT ME** void SetPosition(int depth)
  * [[StarMap]]
    * **DOCUMENT ME** [Body? body] StarMap:GetBodies()
    * **DOCUMENT ME** [System? system] StarMap:GetSystems()
  * [[Telescope]]
    * **DOCUMENT ME** Coordinate? GetCoordinate(int x1, int y1, int x2, int y2)
  * [[Speaker]]
    * **DOCUMENT ME** void Speaker:PlaySound(int soundId)
    * **DOCUMENT ME** void Speaker:ClearSounds()
    * **DOCUMENT ME** void Speaker:Chat(string message)
  * [[Microcontroller]]
    * **DOCUMENT ME** void? Microcontroller:Communicate(any data)
* [[ScreenObject]]
  * **DOCUMENT ME** void ScreenObject:ChangeProperties([\<string\>property=\<any\>value] properties)
* [[Cursor]]
  * **DOCUMENT ME** int Cursor.X
  * **DOCUMENT ME** int Cursor.Y
  * **DOCUMENT ME** string Cursor.Player
  * **DOCUMENT ME** boolean Cursor.Pressed
* **DOCUMENT ME** [[Coordinate]]
