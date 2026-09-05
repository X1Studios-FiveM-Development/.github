# Installation

## X1Studios Advanced Godmode

### Requirements

X1Studios Advanced Godmode does not require a FiveM framework.

It can be installed on:

* Standalone servers
* QBCore servers
* QBox servers
* ESX servers
* vMenu servers
* Custom framework servers

The administrative permission system is handled through the included `permissions.cfg` file.

***

## Step 1 — Download The Resource

Download the latest version of **X1Studios Advanced Godmode**.

Extract the resource using:

* 7-Zip
* WinRAR
* Windows File Explorer

Keep the resource's original file structure intact.

***

## Step 2 — Add The Resource To Your Server

Place the Advanced Godmode resource into your server's resources directory.

For example:

```
resources/
├── [standalone]/
│
└── X1S-GodMode/
```

The exact resource folder name may differ depending on the version you downloaded.

***

## Step 3 — Configure config.lua

Open:

```
config.lua
```

inside the Advanced Godmode resource.

Locate the permanent godmode setting.

The option controls whether godmode should automatically remain active for the entire duration of the server.

#### Permanent Godmode Enabled

When enabled:

* Godmode automatically activates when the server starts.
* The `Godmode Active` UI is displayed.
* The administrator command is disabled.
* Godmode remains active until the server shuts down.

#### Permanent Godmode Disabled

When disabled:

* Godmode is controlled through the administrator command.
* Authorized administrators can toggle godmode.
* The `Godmode Active` UI appears when godmode is enabled.

***

## Step 4 — Configure permissions.cfg

Open the included:

```
permissions.cfg
```

file.

This file controls who is authorized to use the administrative godmode command.

Add the appropriate identifiers or permissions according to the format provided in the resource.

Only trusted administrators should be granted access.

***

## Step 5 — Add Permissions To server.cfg

Make sure your `permissions.cfg` is loaded according to the resource's provided configuration.

If the installation package includes a specific permissions configuration line or setup instruction, follow the format included with your version of the script.

Do not modify the permission structure unless you understand how your server's ACE permissions are configured.

***

## Step 6 — Add The Resource To server.cfg

Open your:

```
server.cfg
```

Add the Advanced Godmode resource:

```cfg
ensure X1S-GodMode
```

Make sure the resource name matches the actual folder name inside your resources directory.

Because the script is standalone, no framework resource is required before it.

***

## Step 7 — Restart The Server

Restart your FiveM server after completing the installation and configuration.

You can also start the resource manually through the server console:

```
ensure X1S-GodMode
```

Check the server console for any errors.

***

## Step 8 — Test Administrative Godmode

If permanent godmode is disabled, connect to the server using an account that has been granted permission.

Use the configured administrative godmode command.

Verify that:

1. Godmode activates.
2. The `Godmode Active` UI appears.
3. The player is protected from damage.
4. The command can disable godmode.
5. The UI disappears when godmode is disabled.

***

## Step 9 — Test Permanent Godmode

If you have enabled permanent godmode in `config.lua`, restart the server.

After joining the server, verify that:

```
Godmode Active
```

automatically appears.

Test whether the player remains protected after:

* Taking damage
* Leaving and entering vehicles
* Moving around the map
* Performing normal gameplay actions

The administrative command should be disabled while permanent mode is active.

***

## Troubleshooting

### Godmode Does Not Activate

If godmode does not activate:

* Verify the resource is running.
* Check the server console for errors.
* Check the client console for errors.
* Verify your permissions.
* Verify the configuration.
* Restart the resource.

***

### Admin Command Does Not Work

If the administrative command does not work:

* Verify permanent godmode is disabled.
* Verify your identifier is correctly configured in `permissions.cfg`.
* Verify the resource is running.
* Check the server console for errors.
* Restart the resource.

Remember that the administrative command is intentionally disabled when permanent godmode is enabled.

***

### "Godmode Active" Does Not Appear

If godmode is active but the UI does not appear:

* Check the client console for errors.
* Verify the resource's UI files are present.
* Restart the resource.
* Restart your FiveM client.
* Verify you are running the latest version.

***

### Permanent Godmode Is Not Working

If permanent godmode does not automatically activate:

1. Open `config.lua`.
2. Verify permanent mode is enabled.
3. Save the configuration.
4. Restart the resource.
5. Reconnect to the server.
6. Check the server and client consoles for errors.

***

### Admin Command Still Works During Permanent Mode

If the admin command is still available while permanent mode is enabled:

* Verify you are running the correct version of the script.
* Confirm the permanent mode setting is actually enabled.
* Restart the resource.
* Restart the server.

Permanent mode is designed to disable the administrative toggle command.

***

## Updating The Script

Before updating X1Studios Advanced Godmode:

1. Stop the existing resource.
2. Back up `config.lua`.
3. Back up `permissions.cfg`.
4. Download the latest version.
5. Replace the old resource files.
6. Reapply your configuration.
7. Start the resource.
8. Test the admin command.
9. Test permanent mode if enabled.
10. Verify the `Godmode Active` UI.

Always check the release information included with the version you are installing.

***

## Installation Complete

X1Studios Advanced Godmode is now installed and ready for use.

The script can operate in either:

**Administrative Mode**

Authorized staff can manually toggle godmode using the administrative command.

**Permanent Mode**

Godmode automatically remains active from server startup until server shutdown, with the administrative command disabled.

When active, players will see:

```
Godmode Active
```

at the top of their screen.

For support, open a ticket in the official X1Studios Discord.

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
