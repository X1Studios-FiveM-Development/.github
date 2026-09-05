# Installation

## X1Studios Advanced Vehicle Flip System

### Installation Guide

This guide will walk you through installing the **X1Studios Advanced Vehicle Flip System** on your FiveM server.

The resource is fully standalone and requires **no dependencies**.

***

### Requirements

**Required Dependencies:**

```
None
```

The script does not require:

* QBCore
* QBox
* ESX
* ox\_lib
* vMenu
* Any other framework
* Any external dependency

***

## 1. Download The Resource

Download the latest version of the **X1Studios Advanced Vehicle Flip System**.

Extract the downloaded archive using a program such as:

* 7-Zip
* WinRAR

After extraction, you should have the resource folder.

***

## 2. Locate Your Resources Folder

Navigate to your FiveM server's resources directory.

A typical server structure may look like:

```
server-data/
└── resources/
    ├── [standalone]/
    ├── [scripts]/
    └── X1S-AdvVehicleFlip/
```

You can place the resource inside an existing resource category or create an X1Studios category.

For example:

```
resources/
└── [X1Studios]/
    └── X1S-AdvVehicleFlip/
```

***

## 3. Verify The Resource Structure

Make sure the resource files are directly inside the resource folder.

Example:

```
X1S-AdvVehicleFlip/
├── fxmanifest.lua
├── client.lua
├── config.lua
└── ...
```

The exact files may vary depending on the version of the resource.

#### Incorrect Structure

```
X1S-AdvVehicleFlip/
└── X1S-AdvVehicleFlip/
    ├── fxmanifest.lua
    └── client.lua
```

#### Correct Structure

```
X1S-AdvVehicleFlip/
├── fxmanifest.lua
└── client.lua
```

The `fxmanifest.lua` file should be directly inside the resource folder.

***

## 4. Configure The Resource

If your version includes a configuration file, open it before starting the resource.

Common configuration options may include:

* Flip duration
* Notification settings
* Vehicle interaction settings
* UI options
* Other gameplay settings

For example:

```
config.lua
```

Only modify configuration values that are provided by your version of the resource.

> Do not remove configuration sections unless you know they are not required.

***

## 5. Add The Resource To server.cfg

Open your server's:

```
server.cfg
```

Add:

```cfg
ensure X1S-AdvVehicleFlip
```

Replace `X1S-``AdvVehicleFlip` with the exact name of your resource folder if you renamed it.

For example, if your resource folder is:

```
X1S-AdvVehicleFlip
```

use:

```cfg
ensure X1S-AdvVehicleFlip
```

***

## 6. Start The Resource

Restart your FiveM server.

You can also start the resource directly from the server console:

```
ensure X1S-AdvVehicleFlip
```

If the resource starts successfully, there should be no resource startup errors in the server console.

***

## 7. Test The Vehicle Flip System

Connect to your server and find a vehicle.

Turn the vehicle onto its side or roof for testing purposes.

#### Exit The Vehicle

Make sure you are completely outside of the vehicle.

#### Approach The Vehicle

Stand close to the vehicle you want to recover.

#### Use The Command

Enter:

```
/flipvehicle
```

The system should begin the recovery process.

You should see a notification similar to:

```
Flipping Vehicle - 15s
```

The countdown should continue until the vehicle is recovered.

***

## 8. Test The Animation

While the flip process is active, verify that the player performs the intended flipping animation.

Make sure:

* The animation starts correctly
* The countdown is visible
* The animation does not become stuck
* The vehicle recovers after the timer completes

***

## 9. Test Failure Conditions

It is recommended to test the system in several situations.

#### Inside A Vehicle

Attempt:

```
/flipvehicle
```

while sitting inside a vehicle.

The system should prevent the action.

#### No Nearby Vehicle

Use:

```
/flipvehicle
```

when no vehicle is nearby.

The system should provide an appropriate failure notification.

#### Interrupted Flip

Start a vehicle flip and interrupt the process.

Verify that the system handles the interruption correctly and resets the countdown when required.

***

## Troubleshooting

### `/flipvehicle` Does Nothing

Check the following:

1. The resource is running.
2. The resource name in `server.cfg` is correct.
3. You are outside of the vehicle.
4. You are close enough to a vehicle.
5. There are no client-side errors.

Check your FiveM console for errors.

***

### Resource Will Not Start

Verify that the resource contains:

```
fxmanifest.lua
```

and that it is directly inside the resource folder.

Also verify your `server.cfg`:

```cfg
ensure X1S-AdvVehicleFlip
```

The name must exactly match the resource folder name.

***

### Vehicle Does Not Flip

Make sure you are:

* Outside of the vehicle
* Close to the vehicle
* Targeting a nearby vehicle
* Using the correct command

```
/flipvehicle
```

Also verify that the flip process is not being interrupted.

***

### Countdown Does Not Appear

Check that the resource's UI/notification files are present and that there are no client-side errors.

If you modified the resource files, restore the original files and test again.

***

### Animation Does Not Play

Verify that the resource was installed completely and that none of the animation-related files were removed or modified.

Check the FiveM client console for errors if the problem persists.

***

## Updating The Resource

When a new version becomes available:

1. Stop your FiveM server.
2. Back up your current resource.
3. Download the latest version.
4. Remove the old resource files.
5. Install the new version.
6. Reapply any custom configuration.
7. Verify `server.cfg`.
8. Restart the server.
9. Test `/flipvehicle`.

Always keep a backup of your configuration before updating.

***

## Installation Complete

The **X1Studios Advanced Vehicle Flip System** is now installed and ready for use.

Players can recover overturned vehicles using:

```
/flipvehicle
```

For support, updates, previews, and assistance, join the X1Studios Discord:

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

**X1Studios - FiveM Development**
