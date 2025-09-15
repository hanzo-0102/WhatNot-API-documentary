# WhatNot Documentary

This document provides an overview of the **WhatNot API** mod, describing all classes, interfaces, and functions it defines.
To use this in your mod, write next import necessary content from **Features** class: 
```java
import com.creatorsindrome.whatnot.Features.*;
```

## Class `Point`

The `Point` class provides functionality related to point operations in Euclidean 2-dimensional geometry.

### Methods

#### `Point()`


| Parameter | Description           |
|-----------|-----------------------|
| `float x` | X coordinate of point |
| `float y` | Y coordinate of point |

- If you create new point without x and y - it's coordinates will be set to (0, 0)

#### `distanceTo()`

**Returns:** `float`

Distance to second point

| Parameter | Description               |
|-----------|---------------------------|
| `Point sec` | Point to find distance to |

## Class `Snail`

The `Snail` class provides functionality related to operations with spiral, coming from center and rotating in opposite to clock direction.

### Methods

#### `Snail()`

| Parameter | Description                                     |
|-----------|-------------------------------------------------|
| `float step` | Size of cell sector (need to be greater than 0) |

#### `getCircle()`

**Returns:** `int`

Get number of circle-layer from center

| Parameter | Description    |
|-----------|----------------|
| `int num` | Number of cell |

#### `getCell()`

**Returns:** `Point`

Get `Point` class variable with coordinated of specific cell

| Parameter | Description |
|-----------|-------------|
| `int num` | Number of cell |

## Class `TaskScheduler`

The `TaskScheduler` class allows you to schedule tasks for running.

### Methods

#### `schedule()`

**Returns:** nothing

Add task to wait it's time

| Parameter | Description                                  |
|-----------|----------------------------------------------|
| `int delayTicks` | Amount of ticks before running               |
| `Runnable task` | Function you want to run on the end of timer |

- Timer always grows, you may face troubles with adding new tasks, recommended to use `resetTimer()` after running your function

#### `resetTimer()`

**Returns:** nothing

Resets timer variable

## Class `TooltipHelper`

The `TooltipHelper` class which allows you to add tooltip to any item in game.

### Methods

#### `addTooltip()`

**Returns:** nothing

Adding tooltip to 

| Parameter | Description                                      |
|-----------|--------------------------------------------------|
| `Component displayname` | Display name of item for tooltip to display with |
| `Component tooltip` | Tooltip to display                               |

## Class `ClientMessageHelper`

The `ClientMessageHelper` class provides functionality related to clientmessagehelper operations.

### Methods

#### `sendNextTick()`

**Returns:** nothing

Adds message to queue before sending it to player's chat

| Parameter | Description        |
|-----------|--------------------|
| `Component message` | Message to display |

#### `clearQueue()`

**Returns:** nothing

Clears queue of messages

## Interface `GFunction`

The `GFunction` interface defines a contract for generic functions. Classes implementing this interface represent specific mathematical or logical functions.

## Mathematical function classes

The following classes implement `GFunction`, each representing a specific function.

| Class | Represents                                | Parameters                  |
|-------|-------------------------------------------|-----------------------------|
| `GLinary` | Represents $$y = kx + b$$ function        | `float k, float b`          |
| `GBinary` | Represents $$y = ax^2 + bx + c$$ function | `float a, float b, float c` |
| `GPower` | Represents $$y = ax^n$$ function          | `float a, float n`          |
| `GLogarithm` | Represents $$y = log_a x$$ function           | `float a`                   |
| `GSin` | Represents $$y = a * sin(x)$$ function        | `float a`                   |
| `GCos` | Represents $$y = a * cos(x)$$ function        | `float a`                   |
| `GTan` | Represents $$y = a * tg(x)$$ function         | `float a`                   |
| `GCtan` | Represents $$y = a * ctg(x)$$ function        | `float a`                   |
| `GHyperbole` | Represents $$y = k / x + b$$ function       | `float k, float b`          |

### Functions for each class

#### `getY()`

**Return:** `float`

Gives you Y coordinate, based on X for your function. Or NULL if function is not existing on provided X


| Parameter | Description  |
|-----------|--------------|
| `int x`   | X coordinate |

#### `doesOn()`

**Return:** `boolean`

Checks if point is laying on your function graphic

| Parameter     | Description        |
|---------------|--------------------|
| `Point point` | Point for checking |

#### `intersection()`

**Return:** `Point` or `null`

Returns first point of intersection between two functions on given distance. Works up to 3 digits after point

| Parameter     | Description        |
|---------------|--------------------|
| `GFunction sec` | Second function to compare |
| `float start` | Begining of search |
| `float end`| End of search |

# Functions


#### `newItemTag()`

**Returns:** `TagKey<Item>`

Returns created item tag within provided information

| Parameter | Description             |
|-----------|-------------------------|
| `String modid` | Mod id to create tag in |
| `String name` | Tag name                |

#### `newBlockTag()`

**Returns:** `TagKey<Block>`

Returns created block tag within provided information

| Parameter | Description             |
|-----------|-------------------------|
| `String modid` | Mod id to create tag in |
| `String name` | Tag name                |

#### `newBiomeTag()`

**Returns:** `TagKey<Biome>`

Returns created biome tag within provided information

| Parameter | Description             |
|-----------|-------------------------|
| `String modid` | Mod id to create tag in |
| `String name` | Tag name                |

#### `newEntityTypeTag()`

**Returns:** `TagKey<EntityType<?>>`

Returns created entity type tag within provided information

| Parameter | Description             |
|-----------|-------------------------|
| `String modid` | Mod id to create tag in |
| `String name` | Tag name                |

#### `isModLoaded()`

**Returns:** `boolean`

Returns `true` if mod is loaded 

| Parameter | Description |
|-----------|-------------|
| `String modId` | Your mod id |
