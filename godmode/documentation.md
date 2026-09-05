# Documentation

## X1Studios Advanced Godmode

### Overview

The **X1Studios Advanced Godmode** is a lightweight FiveM administration utility designed to provide authorized staff with a simple and reliable godmode system.

The script provides an administrator-controlled godmode command, a configurable **permanent godmode mode**, and a clean on-screen indicator showing when godmode is active.

Permissions are handled through a dedicated **`permissions.cfg`** file, allowing server owners to control exactly who has access to the administrative command.

***

## Features

### Admin Godmode Command

Authorized administrators can toggle godmode through the provided admin command.

When enabled, the player becomes protected from normal player damage.

The command can be used to:

* Enable godmode
* Disable godmode
* Quickly toggle protection during administrative situations

Access to the command is controlled through the script's permissions system.

***

## Permissions.cfg

The administrative command uses a dedicated:

```
permissions.cfg
```

file.

This allows server owners to define which players or identifiers are authorized to use the godmode command.

The permissions file keeps administrative access separate from the main script configuration, making it easier to manage staff permissions.

***

## Permanent Godmode

X1Studios Advanced Godmode includes an option to keep godmode enabled permanently.

This feature can be enabled or disabled through:

```
config.lua
```

When permanent godmode is enabled, godmode remains active from the moment the server starts until the server shuts down.

#### Permanent Mode

When enabled:

* Godmode automatically activates
* Players remain protected while the server is running
* The admin command is disabled
* Godmode cannot be manually toggled through the command

This mode is useful for servers or environments where godmode should always remain active.

***

## Admin Command Disable

When permanent godmode is enabled, the administrative godmode command is automatically disabled.

This prevents administrators from accidentally turning off the protection while the permanent mode is active.

If you want administrators to manually toggle godmode, permanent mode should be disabled in `config.lua`.

***

## Godmode Active UI

When godmode is active, the script displays a:

```
Godmode Active
```

indicator at the top of the player's screen.

This provides an immediate visual confirmation that godmode is currently enabled.

The indicator helps prevent administrators from accidentally assuming godmode is disabled when it is still active.

***

## UI

The default UI displays:

```
Godmode Active
```

at the top of the screen.

The UI is designed to be:

* Simple
* Lightweight
* Easy to identify
* Non-intrusive
* Suitable for administrative use

***

## How Godmode Works

The system can operate in two different modes.

#### Administrative Mode

When permanent mode is disabled:

**1.** An authorized administrator uses the godmode command.

**2.** Godmode is enabled.

**3.** The `Godmode Active` UI appears.

**4.** The administrator can use the command again to disable godmode.

**5.** The UI disappears when godmode is disabled.

#### Permanent Mode

When permanent mode is enabled:

**1.** The server starts.

**2.** Godmode automatically activates.

**3.** The `Godmode Active` UI appears.

**4.** The administrative command is disabled.

**5.** Godmode remains active until the server shuts down.

***

## Configuration

The primary configuration is located inside:

```
config.lua
```

The configuration can be used to control whether the script operates in permanent godmode mode.

#### Permanent Godmode

Enable or disable the permanent mode according to your server's requirements.

When enabled, the admin command is automatically disabled.

***

## Requirements

The script is designed to be lightweight and standalone.

No FiveM framework is required.

It can be used on servers running:

* Standalone
* QBCore
* QBox
* ESX
* vMenu
* Custom frameworks

The script's permission system is handled independently through `permissions.cfg`.

***

## Performance

X1Studios Advanced Godmode is designed to be lightweight and have minimal impact on server performance.

The system performs only the checks required to maintain the player's godmode state and UI.

***

## Preview

Watch the X1Studios Advanced Godmode preview:

[https://www.youtube.com/watch?v=Vn0HJ0SkJ-o](https://www.youtube.com/watch?v=Vn0HJ0SkJ-o)

***

## Support

For support with X1Studios Advanced Godmode, open a support ticket in the official X1Studios Discord.

**Support is provided through Discord tickets only.**

#### X1Studios Discord

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

***

## Community

Join the X1Studios Discord for:

* Upcoming FiveM scripts
* Free FiveM EUP packs
* Custom liveries
* Development previews
* New releases
* Updates
* Support

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
