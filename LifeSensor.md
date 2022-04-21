A device which senses life in a region. Is used to get the players and their positions in the local region.

## Table of contents

### Methods
* [`dictionary LifeSensor:GetReading()`](#dictionary-lifesensorgetreading)

___

## `dictionary LifeSensor:GetReading()`

> Gets the life in the local region. Returns a dictionary where each key is the name of a player, and each value is their position in the world. Has a range of 2000 studs.

> An example of the format can be seen below: 
> ```lua
> {
>  ["PLAYER_NAME"] = VECTOR3_POSITION;
>  ["PLAYER_NAME2"] = VECTOR3_POSITION;
>  ["PLAYER_NAME3"] = VECTOR3_POSITION;
> }
> ```
> where `PLAYER_NAME` is the player's name, and `VECTOR3_POSITION` is the position of the player
