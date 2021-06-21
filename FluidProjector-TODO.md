A part which projects someone's avatar above it.

## Table of contents

### Properties

* [`Vector3 FluidProjector.Size`](#vector3-fluidprojectorsize)
* [`string<Fluid> FluidProjector.Fluid`](#stringfluid-fluidprojectorfluid)

### Events

* [`Signal FluidProjector.Configured`](#signal-fluidprojectorconfigured)

___

## `Vector3 FluidProjector.Size`

**Default**: `Vector3.new(10, 10, 10)`
> The volume of fluid to project.

___

## `string<Fluid> FluidProjector.Fluid`

**Default**: `"Water"`
> The type of fluid to project.

___

## `Signal FluidProjector.Configured`

> Fires when the FluidProjector is reconfigured