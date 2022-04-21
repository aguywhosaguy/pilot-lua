A part used to store data from microcontrollers.

## Table of contents

### Methods
* [`void Disk:ClearDisk()`](#void-diskcleardisk)
* [`void Disk:Write(string key, string value)`](#void-diskwritestring-key-string-data)
* [`string Disk:Read(string key)`](#string-diskreadstring-key)
* [`dictionary Disk:ReadEntireDisk()`](#dictionary-diskreadentiredisk)
___

## `void Disk:ClearDisk()`

> Clears ALL information on the disk.

___

## `void Disk:Write(string key, string data)`

> Writes the `data` to the given `key` on the disk.

___

## `string Disk:Read(string key)`

> Reads the data from the given `key` on the disk and returns it.

___

## `dictionary Disk:ReadEntireDisk()`

> Reads all data from the Disk and returns it as a dictionary.