# pilot.lua
Unofficial Waste of Space Microcontroller Documentation ([[Additional Resources|Additional-Resources]])

## Globals
* [[Microcontroller Globals|Microcontroller-Globals]]
* [[Roblox Globals|Roblox-Globals]]

## Parts (TO BE DOCUMENTED)
* EnergyShield
  * **DOCUMENT ME** EnergyShield:GetShieldHealth()
* Disk
  * **DOCUMENT ME** void Disk:ClearDisk()
  * **DOCUMENT ME** void Disk:Write(string key, string data)
  * **DOCUMENT ME** string Disk:Read(string key)
* Modem
  * **DOCUMENT ME** void Modem:PostRequest(string domain, string data) - NOTE: NOT HTTP
  * **DOCUMENT ME** string Modem:GetRequest(string domain) - NOTE: NOT HTTP
  * **DOCUMENT ME** void Modem:SendMessage(string data, int id) - Sends a message (Like `MessagingService`) and has an event on the Modem (need to find event name, I believe its OnMessage)
* Screen
  * **DOCUMENT ME** Vector2 Screen:GetDimensions()
  * **DOCUMENT ME** void Screen:ClearElements(dictionary? properties)
  * **DOCUMENT ME** GuiElement Screen:CreateElement(string elementClass, dictionary properties)
  * TouchScreen
    * **DOCUMENT ME** Cursor? TouchScreen:GetCursor()
    * **DOCUMENT ME** array TouchScreen:GetCursors()
* Rail
  * **DOCUMENT ME** void SetPosition(int depth)
* StarMap
  * **DOCUMENT ME** array StarMap:GetBodies()
  * **DOCUMENT ME** array StarMap:GetSystems()
* Telescope
  * **DOCUMENT ME** Coordinate? GetCoordinate(int x1, int y1, int x2, int y2)
* Speaker
  * **DOCUMENT ME** void Speaker:PlaySound(int soundId)
  * **DOCUMENT ME** void Speaker:ClearSounds()
  * **DOCUMENT ME** void Speaker:Chat(string message)
* Microcontroller
  * **DOCUMENT ME** void? Microcontroller:Communicate(any data)
* Keyboard
  * **DOCUMENT ME** void Keyboard:SimulateKeyPress(string? key, string Player)
  * **DOCUMENT ME** void Keyboard:SimulateTextInput(string? input, string Player)
* LifeSensor
  * **DOCUMENT ME** map<[Player]=Vector3> LifeSensor:GetReading()
* Instrument
  * **DOCUMENT ME** number Instrument:GetReading(string typeName=nil) - When type name is unspecified, returns current sensor data