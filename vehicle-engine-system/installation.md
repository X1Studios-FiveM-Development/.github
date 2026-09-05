# Installation

## X1Studios Vehicle Engine System

### Installation Guide

This guide explains how to install and configure the **X1Studios Vehicle Engine System** on your FiveM server.

The resource is **fully standalone** and requires no external dependencies.

***

## Requirements

**Required Dependencies:**

```
None
```

The resource does not require:

* QBCore
* QBox
* ESX
* ox\_lib
* vMenu
* Any other framework
* Any additional resources

***

## 1. Download The Resource

Download the latest version of the **X1Studios Vehicle Engine System**.

Extract the downloaded archive using:

* 7-Zip
* WinRAR

Once extracted, you should have the resource folder.

***

## 2. Locate Your Resources Folder

Navigate to your FiveM server's resources directory.

A typical structure may look like:

```
server-data/
└── resources/
    ├── [standalone]/
    ├── [scripts]/
    └── X1S-VehEngSystem/
```

You can place the resource inside an existing category or create an X1Studios category.

For example:

```
resources/
└── [X1Studios]/
    └── X1S-VehEngSystem/
```

***

## 3. Verify The Resource Structure

Make sure the resource files are directly inside the resource folder.

For example:

```
X1S-VehEngSystem/
├── fxmanifest.lua
├── client.lua
├── config.lua
└── ...
```

The exact file names may vary depending on the version of the resource.

#### Incorrect

```
X1S-VehEngSystem/
└── X1S-VehEngSystem/
    ├── fxmanifest.lua
    └── ...
```

#### Correct

```
X1S-VehEngSystem/
├── fxmanifest.lua
└── ...
```

The `fxmanifest.lua` file should be directly inside the resource folder.

***

## 4. Configure The Resource

If your version includes a configuration file, open it before starting the resource.

Common settings may include:

* Engine behavior
* Engine failure chance
* Notification settings
* Keybind behavior
* Other engine-related settings

For example:

```
config.lua
```

Only modify settings that are actually included in your version of the resource.

> Keep the existing configuration structure intact to prevent configuration errors.

***

## 5. Add The Resource To server.cfg

Open your:

```
server.cfg
```

Add the resource:

```cfg
ensure X1S-VehEngSystem
```

If you renamed the resource folder, use the exact folder name.

For example:

```
X1Studios-VehicleEngine
```

would require:

```cfg
ensure X1Studios-VehEngSystem
```

The resource name in `server.cfg` must match the resource folder name exactly.

***

## 6. Start The Resource

Restart your FiveM server after adding the resource.

Alternatively, you can start it through the server console:

```
ensure X1S-VehEngSystem
```

Check the server console for any errors.

***

## 7. Test The Engine System

Connect to your server and enter a vehicle.

The engine should remain **off** rather than automatically starting.

You should receive the appropriate on-screen hint.

For example:

```
Press [G] or use /eng to start engine
```

***

## 8. Test The G Keybind

While inside the vehicle, press:

```
G
```

The engine should toggle.

Verify that:

* The engine starts
* The hint disappears
* The engine can be turned off again
* Notifications appear correctly

***

## 9. Test The Commands

Test both available commands.

#### Primary Command

```
/eng
```

#### Alternative Command

```
/engine
```

Both commands should toggle the vehicle engine.

***

## 10. Test Engine Persistence

Start a vehicle engine and exit the vehicle.

Verify that the engine remains running.

Then re-enter the vehicle and confirm that the vehicle maintains its appropriate engine state.

Repeat the test with the engine turned off.

***

## 11. Test Engine Failure

If engine failure is enabled in your configuration, repeatedly attempt to start a vehicle.

The system may randomly cause the engine to fail during startup.

This allows you to verify that the engine failure functionality is working correctly.

***

## 12. Test The Notifications

Verify that the NUI notifications are displaying correctly.

Check:

#### Top-Right Notifications

Engine-related alerts should appear in the top-right corner.

#### Bottom-Center Hint

When the engine is off, the instructional hint should appear at the bottom center.

Once the engine starts, the hint should disappear automatically.

***

## Keybind Configuration

The default keybind is:

```
G
```

FiveM allows players to change their keybind through the game's keybind settings.

The `/eng` and `/engine` commands remain available even if the player changes their keybind.

> **Recommended:** Keep the default G keybind unless it conflicts with another resource or server function.

***

## Troubleshooting

### Engine Automatically Starts

If vehicles are still automatically starting, verify that the resource is running correctly.

Check:

```cfg
ensure X1S-VehEngSystem
```

Also check the FiveM client console for errors.

***

### `/eng` Does Not Work

Verify:

1. The resource is running.
2. You are inside a vehicle.
3. The resource name in `server.cfg` is correct.
4. There are no client-side errors.

Test:

```
/engine
```

as an alternative.

***

### G Key Does Not Work

Check your FiveM keybind settings.

The default key is:

```
G
```

If the key has been changed or is being used by another resource, restore the appropriate binding or choose another key.

***

### Engine Failure Is Not Working

If your version includes configurable engine failure settings, verify that the feature is enabled and configured correctly.

Check the resource configuration for the appropriate engine failure settings.

***

### Notifications Are Not Appearing

Verify that the resource was installed completely.

Check that:

* All NUI files are present.
* The resource is running.
* No files were accidentally removed.
* No client-side errors are present.

If you modified the resource files, restore the original files and test again.

***

### Engine State Is Not Persistent

Make sure the resource is running without errors.

Test the behavior by:

1. Starting the vehicle.
2. Exiting the vehicle.
3. Waiting briefly.
4. Re-entering the vehicle.
5. Checking the engine state.

If the issue continues, check the client console for errors.

***

## Updating The Resource

When a new version is released:

1. Stop your FiveM server.
2. Back up your current resource.
3. Download the newest version.
4. Remove the old resource files.
5. Install the updated version.
6. Restore your configuration/customizations.
7. Verify `server.cfg`.
8. Restart your server.
9. Test the engine system.

Always back up your configuration before updating.

***

## Installation Complete

Your **X1Studios Vehicle Engine System** is now installed and ready to use.

Players can control their vehicle engines with:

```
G
```

or:

```
/eng
```

or:

```
/engine
```

For support, updates, previews, and assistance, join the X1Studios Discord:

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

**X1Studios - FiveM Development**
