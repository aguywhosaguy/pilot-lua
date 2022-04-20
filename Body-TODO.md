An array of information about the stellar body. Received from [StarMap:GetBodies()](https://github.com/iimurpyh/pilot-lua/wiki/StarMap#body-starmapgetbodies)
## Table of contents

-  [`string PlanetType`](#string-planettype)
-  [`table Beacons`](#tablebeacons)

## `string PlanetType`
> Gives you information about the body's planet type (e.g. Barren, Exotic, Forest)
## `table Beacons`
> Gives you a table of Beacon tables if the Body has one or more active beacons.  If the beacon's ShowOnMap value is set to True, the table will contain the name of that beacon. Otherwise, the table will contain coordinates of the Body that the Beacon is placed on. **(Presumably, the Beacons table will only contain one Beacon. Needs to be tested)**