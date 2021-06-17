# LifeSensor
A device which senses life in a region. Is used to get all of the players and their positions in the local region.

## Table of contents
* [`map<[Player]=Vector3> LifeSensor:GetReading()`](#mapplayervector3-lifesensorgetreading)

___

## `map<[Player]=Vector3> LifeSensor:GetReading()`

> Gets all of the life in the local region. Returns a dictionary where each key is the name of a player, and each value is their position in the world.