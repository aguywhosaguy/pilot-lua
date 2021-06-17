A device which can measure various things in the environment such as Temperature, or Velocity.

## Table of Contents
* [`number Instrument:GetReading(int typeId=nil)`](#number-instrumentgetreadingint-typeidnil)

___

## `number Instrument:GetReading(int typeId=nil)`

> Gets the reading from the sensor. You can also pass an integer value type and the Instrument will return that reading type.

### Valid types
* `0` - Velocity
* `1` - Rotational Velocity
* `2` - Temperature
* `3` - Region time
* `4` - Available power
* `5` - Attached part size
* `6` - Position in the region