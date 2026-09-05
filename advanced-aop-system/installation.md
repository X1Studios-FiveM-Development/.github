# Installation

## X1Studios Advanced AOP System

### Requirements

X1Studios Advanced AOP System requires **nothing**.

The resource is completely standalone and does not require:

* QBCore
* QBox
* ESX
* ox\_lib
* Any other framework
* Any external dependency

***

## Step 1 — Download The Resource

Download the latest version of **X1Studios Advanced AOP System**.

Extract the downloaded resource using a program such as:

* 7-Zip
* WinRAR
* Windows File Explorer

Make sure the resource remains in its original folder structure.

***

## Step 2 — Add The Resource To Your Server

Place the AOP resource into your server's resources directory.

For example:

```
resources/
├── [standalone]/
│
└── X1S-AdvAOPSystem/
```

The folder name may be different depending on the version you downloaded.

Do not rename individual files inside the resource.

***

## Step 3 — Configure The Resource

Open the configuration file included with the resource.

Configure the available settings according to your server.

Depending on the version of the script, configuration options may include:

* AOP locations
* AOP names
* ACE permissions
* Discord permissions
* Discord webhook
* UI settings
* Display settings
* Other system options

Save the configuration after making your changes.

***

## Step 4 — Configure AOP Locations

Add or modify the available AOP locations using the configuration provided with the script.

AOP locations can represent areas such as:

```
Los Santos
Blaine County
Sandy Shores
Paleto Bay
Vespucci
Downtown Los Santos
```

You can configure the available locations to match your server's roleplay structure.

***

## Step 5 — Configure Permissions

Configure the ACE permission used to access the AOP management menu.

Make sure the permission is only assigned to trusted staff members.

If Discord role permissions are being used, verify that your Discord role integration is configured correctly.

Players without the required permission should not be able to access or modify the AOP.

***

## Step 6 — Configure Discord Logging

If you want AOP changes to be logged to Discord, configure the Discord webhook in the resource configuration.

Paste your Discord webhook URL into the appropriate configuration option.

Example:

```
Discord Webhook = "YOUR_WEBHOOK_URL"
```

Do not publicly share your webhook URL.

After configuring the webhook, save the configuration.

***

## Step 7 — Add The Resource To server.cfg

Open your server's:

```
server.cfg
```

Add the AOP resource to your startup configuration.

For example:

```cfg
ensure X1S-AdvAOPSystem
```

Make sure the resource name matches the actual folder name inside your resources directory.

Because the system is fully standalone, no framework resource needs to be started before it.

***

## Step 8 — Restart The Server

Restart your FiveM server after installing and configuring the resource.

You can also start the resource directly from the server console:

```
ensure X1S-AdvAOPSystem
```

Check your server console for any errors.

***

## Step 9 — Test Permissions

Join the server using an account that has the required staff permissions.

Open the AOP management system and verify that you can access the AOP selection menu.

Then test the system with an account that does **not** have the required permission.

The unauthorized account should not be able to change the AOP.

***

## Step 10 — Test AOP Changes

Select an AOP from the management menu.

Verify that:

1. The AOP changes successfully.
2. The new AOP is displayed to players.
3. Other players receive the updated AOP.
4. The Discord webhook receives the change if logging is enabled.
5. The staff member responsible for the change is correctly recorded.

***

## Troubleshooting

### AOP Menu Does Not Open

If the AOP management menu does not open:

* Verify the resource is running.
* Check the server console for errors.
* Verify your ACE permissions.
* Verify your Discord role permissions if applicable.
* Restart the resource.
* Make sure the resource name in `server.cfg` is correct.

***

### Players Cannot See The AOP

If the AOP UI does not appear:

* Verify that the resource started successfully.
* Check the client console for errors.
* Verify the UI configuration.
* Restart the resource.
* Restart the FiveM client and reconnect to the server.

***

### Discord Permissions Are Not Working

If Discord-based permissions are not functioning:

* Verify the required Discord role is assigned.
* Verify the ACE permission configuration.
* Check your Discord integration.
* Make sure the Discord identifier is being recognized correctly.
* Restart the server after changing permissions.

***

### Discord Logs Are Not Sending

If AOP changes are not appearing in Discord:

* Verify the webhook URL.
* Make sure the webhook has not been deleted.
* Verify that the webhook is configured in the correct configuration option.
* Check the server console for errors.
* Create a new Discord webhook and test again if necessary.

***

### AOP Changes Are Not Saving

If the selected AOP does not update:

* Check the server console for errors.
* Verify that the selected AOP exists in the configuration.
* Verify that the resource is running.
* Restart the resource.
* Check the configuration for formatting or syntax errors.

***

## Updating The Script

When installing a new version of X1Studios Advanced AOP System:

1. Stop the current resource.
2. Back up your configuration.
3. Download the latest version.
4. Replace the old resource files.
5. Reapply your configuration if necessary.
6. Start the resource.
7. Test the AOP system.
8. Verify Discord permissions and logging.

Always review the release information for the version you are installing before updating.

***

## Installation Complete

X1Studios Advanced AOP System is now installed and ready for use.

The system can now be used to manage your server's active Area of Patrol while keeping players informed through the AOP UI.

For support, open a ticket in the official X1Studios Discord.

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
