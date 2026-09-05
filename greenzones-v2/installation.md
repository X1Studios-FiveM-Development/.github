# Installation

## X1Studios GreenZone System v2

### Installation Guide

This guide will walk you through installing **X1S-GreenZones** and setting up the required **PolyZone** dependency and ACE permissions.

***

## Requirements

Before installing X1S-GreenZones, make sure your server has:

#### Required

**PolyZone**

GitHub:

[https://github.com/mkafrin/PolyZone](https://github.com/mkafrin/PolyZone)

#### Built-In

**ACE Permissions**

ACE permissions are provided through FiveM and do not require an additional framework.

***

## 1. Download X1S-GreenZones

Download the latest version of:

```
X1S-GreenZones
```

Extract the downloaded archive using a program such as:

* 7-Zip
* WinRAR

You should now have the X1S-GreenZones resource folder.

***

## 2. Install PolyZone

Download PolyZone from the official GitHub repository:

[https://github.com/mkafrin/PolyZone](https://github.com/mkafrin/PolyZone)

Extract the PolyZone resource into your server's resources directory.

Your server structure should look similar to:

```
resources/
├── [dependencies]/
│   └── PolyZone/
└── [X1Studios]/
    └── X1S-GreenZones/
```

The exact folder structure can be different depending on how your server organizes resources.

***

## 3. Verify PolyZone

Make sure the PolyZone resource contains its required resource files and is directly inside its resource folder.

For example:

```
PolyZone/
├── fxmanifest.lua
├── client.lua
└── ...
```

Do not place PolyZone inside another nested PolyZone folder.

Incorrect:

```
PolyZone/
└── PolyZone/
    ├── fxmanifest.lua
    └── ...
```

Correct:

```
PolyZone/
├── fxmanifest.lua
└── ...
```

***

## 4. Install X1S-GreenZones

Place the X1S-GreenZones resource inside your FiveM resources directory.

For example:

```
resources/
└── [X1Studios]/
    └── X1S-GreenZones/
```

Make sure the resource files are directly inside the resource folder.

For example:

```
X1S-GreenZones/
├── fxmanifest.lua
├── client.lua
├── server.lua
├── config.lua
└── ...
```

The exact files may differ depending on the version of the resource.

***

## 5. Configure PolyZone Startup

Open your:

```
server.cfg
```

Make sure PolyZone starts before X1S-GreenZones.

For example:

```cfg
ensure PolyZone
ensure X1S-GreenZones
```

If your PolyZone folder has a different name, use the exact resource name.

***

## 6. Configure X1S-GreenZones

If your version includes a configuration file, open the provided configuration file.

For example:

```
config.lua
```

Review the available settings and customize the resource according to your server.

Depending on the version, configuration options may include:

* GreenZone behavior
* Notifications
* Zone settings
* Permission settings
* Other system options

> Do not add or remove configuration values that are not supported by your version of the resource.

***

## 7. Configure ACE Permissions

X1S-GreenZones uses **ACE Permissions** to control access to the administration interface.

You will need to assign the appropriate ACE permission to the staff members or roles that should be able to manage GreenZones.

The exact ACE permission name should be taken from the configuration/documentation included with your version of the resource.

Your `server.cfg` may use an ACE structure similar to:

```cfg
add_ace group.admin <green-zone-permission> allow
```

The exact permission name depends on the resource configuration.

If your server uses Discord-based ACE permissions, ensure the appropriate Discord role is mapped to the ACE group before testing the GreenZone administration system.

***

## 8. Configure Staff Access

After configuring the ACE permission, make sure the intended administrators are assigned to the appropriate ACE group.

For example:

```
Administrator
    ↓
ACE Group
    ↓
GreenZone Permission
    ↓
GreenZone Admin UI
```

Only users with the required permission should be able to access the GreenZone management interface.

***

## 9. Start The Server

Restart your FiveM server after completing the installation.

You can also start the resources manually from the server console:

```
ensure PolyZone
ensure X1S-GreenZones
```

Check the server console for any errors during startup.

***

## 10. Test The Admin UI

Join your FiveM server using an account that has the required ACE permission.

Open the GreenZone administration interface using the method provided by your version of the resource.

Verify that you can:

* Open the admin UI
* Create a GreenZone
* Edit a GreenZone
* Manage existing zones
* Remove a GreenZone

***

## 11. Test GreenZone Detection

Create a test GreenZone in a safe location.

Enter the zone and verify that:

* The zone is detected
* GreenZone restrictions activate
* The appropriate notification appears

Then leave the zone and verify that the system detects your departure and displays the appropriate notification.

***

## 12. Test Permissions

This is an important installation test.

#### Authorized User

Log in as a user with the appropriate ACE permission.

Verify that the GreenZone administration interface is accessible.

#### Unauthorized User

Log in as a normal player without the required ACE permission.

Verify that the user cannot access or manage the GreenZone administration system.

***

## Troubleshooting

### GreenZones Are Not Detecting Players

Verify that PolyZone is running.

Check your `server.cfg`:

```cfg
ensure PolyZone
ensure X1S-GreenZones
```

PolyZone should start before X1S-GreenZones.

Also check the client console for errors.

***

### GreenZone Admin UI Does Not Open

Verify that your player has the required ACE permission.

Check:

* ACE group assignment
* Permission name
* `server.cfg`
* Resource configuration

Make sure the permission name matches the one configured by the resource.

***

### Players Can Access The Admin UI Without Permission

Check your ACE configuration.

Make sure the GreenZone administration permission is not being granted to a broad group unintentionally.

Review all relevant:

```cfg
add_ace
add_principal
```

entries in your server configuration.

***

### PolyZone Errors

Verify that PolyZone is installed correctly and starts before X1S-GreenZones.

Check the server console for PolyZone errors.

Make sure you are using a compatible version of PolyZone.

***

### Notifications Are Not Appearing

Verify that:

* X1S-GreenZones is running
* The notification files are present
* The player is actually entering/leaving the configured zone
* There are no client-side errors

***

### GreenZone Restrictions Are Not Working

First verify that the zone itself is being detected.

If the player receives an enter-zone notification but restrictions are not working, review the individual GreenZone settings and configuration.

***

## Updating X1S-GreenZones

When a new version is released:

1. Stop your FiveM server.
2. Back up your current X1S-GreenZones resource.
3. Back up your configuration.
4. Download the newest version.
5. Replace the old resource files.
6. Restore your custom configuration where applicable.
7. Verify your ACE permissions.
8. Verify PolyZone is still installed correctly.
9. Confirm your `server.cfg`.
10. Restart the server.
11. Test the GreenZone system.

Always keep a backup before updating.

***

## Installation Complete

Your **X1Studios GreenZone System v2** should now be installed and ready for configuration.

You can begin creating protected areas through the **Custom Admin UI** and control administrator access through **ACE Permissions**.

#### Required Resource

**PolyZone:**

[https://github.com/mkafrin/PolyZone](https://github.com/mkafrin/PolyZone)

#### X1Studios Support

**SUPPORT — YES | DISCORD TICKETS ONLY**

For installation help, configuration assistance, or bug reports, open a ticket in the X1Studios Discord:

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

**X1Studios — FiveM Development & Resources**
