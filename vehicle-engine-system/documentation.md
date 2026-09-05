# Documentation

## X1Studios Vehicle Engine System

### Overview

The **X1Studios Vehicle Engine System** is a lightweight, fully standalone FiveM resource designed to bring more realism and immersion to vehicle operation.

Instead of vehicles automatically starting when a player enters them, players have complete control over their engine using a command or keybind.

The system also introduces engine failure, persistent engine states, modern NUI notifications, and smart on-screen hints while maintaining **0.00ms idle performance**.

***

## Features

### Realistic Engine Control

Take full control of your vehicle's engine.

Players can start or stop their engine using:

```
/eng
```

or:

```
/engine
```

A default **G keybind** is also included.

Vehicles will no longer automatically start when a player enters them.

***

### Manual Engine Starting

When entering a vehicle with the engine turned off, the system reminds the player how to start it.

The on-screen hint displays:

```
Press [G] or use /eng to start engine
```

Once the engine is started, the hint automatically disappears.

***

### Engine Failure System

The system can randomly cause an engine to fail when the player attempts to start it.

This adds an additional layer of realism and unpredictability to driving.

Instead of every engine starting perfectly every time, players may occasionally experience a failed startup.

***

### Persistent Vehicle Engine States

Vehicle engine states are maintained during vehicle interactions.

For example:

```
Engine ON
    ↓
Player exits vehicle
    ↓
Engine remains ON
    ↓
Player re-enters vehicle
    ↓
Engine state remains consistent
```

This prevents vehicles from unnecessarily changing engine states simply because the player exited or re-entered.

***

## NUI Notification System

The resource includes a custom NUI notification interface designed to provide clear feedback without obstructing gameplay.

#### Top-Right Notifications

Standard engine-related alerts appear in the **top-right corner** of the screen.

These notifications provide immediate feedback when interacting with the engine.

#### Bottom-Center Hint

A persistent instructional hint can appear at the bottom center of the screen when the player's vehicle engine is off.

Example:

```
Press [G] or use /eng to start engine
```

The hint automatically disappears when it is no longer needed.

***

## Keybind Support

The default engine keybind is:

```
G
```

Players can rebind the key through FiveM's keybind settings.

> **Recommendation:** It is recommended to keep the default G keybind unless your server has another resource already using the same key.

The commands remain available regardless of the configured keybind.

***

## Commands

### `/eng`

Toggles the vehicle engine.

```
/eng
```

***

### `/engine`

Alternative command for toggling the engine.

```
/engine
```

Both commands provide the same core functionality.

***

## How It Works

The basic workflow is simple:

#### 1. Enter A Vehicle

Enter a vehicle as normal.

#### 2. Engine Remains Off

The engine will remain off instead of automatically starting.

#### 3. Start The Engine

Press:

```
G
```

or use:

```
/eng
```

or:

```
/engine
```

#### 4. Engine Starts

If the engine successfully starts, the instructional hint disappears.

#### 5. Engine Failure

Depending on the configured failure behavior, the engine may fail to start.

The player can attempt to start it again.

***

## Performance

The Vehicle Engine System is designed with performance in mind.

#### Idle Performance

```
0.00ms
```

The resource is lightweight and designed to run efficiently without unnecessary processing.

***

## Standalone

The X1Studios Vehicle Engine System is completely standalone.

It does not require:

* QBCore
* QBox
* ESX
* ox\_lib
* vMenu
* Any other framework
* Any external dependency

***

## Compatibility

The system can be used with virtually any FiveM server configuration, including:

* QBCore
* QBox
* ESX
* vMenu
* Custom frameworks
* Standalone servers

Because the system is framework independent, it can be added to an existing server without requiring framework-specific integration.

***

## Customization

The resource is structured to allow server owners to customize supported settings.

Depending on the version of the resource, available configuration options may include:

* Engine behavior
* Engine failure settings
* Notification behavior
* Keybind settings
* Other vehicle-related options

Use the configuration files included with your version of the resource and retain the existing configuration structure.

***

## Perfect For

The X1Studios Vehicle Engine System is especially useful for:

* Roleplay servers
* Economy servers
* Realism-focused communities
* Law enforcement roleplay
* Civilian roleplay
* Racing communities
* Vehicle-focused servers
* Any server wanting improved vehicle immersion

***

## Why Use The X1Studios Vehicle Engine System?

The system adds meaningful vehicle interaction without making the experience unnecessarily complicated.

Players gain:

* Manual engine control
* Realistic engine behavior
* Engine failure mechanics
* Persistent vehicle states
* Keybind support
* Modern notifications
* Helpful on-screen instructions
* Lightweight performance

All while remaining completely standalone.

***

## Requirements

**Requirements:**

```
Nothing
```

The resource has **no external dependencies**.

***

## Support

For installation assistance, configuration help, bug reports, or general support, join the X1Studios Discord.

**Discord:**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

The Discord also includes previews of upcoming X1Studios resources, EUP packs, liveries, scripts, and other releases.

***

## X1Studios

**X1Studios** develops FiveM scripts, EUP packs, liveries, and other resources focused on performance, functionality, and immersion.

Join the Discord for upcoming releases, previews, updates, and support.
