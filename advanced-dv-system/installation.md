# Installation

## X1Studios Advanced Delete Vehicle System

### Requirements

The X1Studios Advanced DV System is completely standalone.

#### FiveM Requirements

* FiveM server

#### Discord Requirements

The Discord permission and logging features require:

* Discord Bot Token
* Discord Guild ID
* Discord Role IDs
* Discord Webhook URL

No framework is required.

***

## Step 1 — Download The Resource

Download the latest version of **X1Studios Advanced DV System**.

Extract the resource using:

* 7-Zip
* WinRAR
* Windows File Explorer

Make sure the resource maintains its original folder structure.

***

## Step 2 — Add The Resource To Your Server

Place the Advanced DV resource inside your server's resources directory.

For example:

```
resources/
├── [standalone]/
│
└── X1S-AdvDVSystem/
```

The exact resource folder name may differ depending on the version you downloaded.

Make sure the resource contains all of its original files.

***

## Step 3 — Open The Configuration

Open the configuration file included with the resource.

The configuration contains the settings required to customize the Advanced DV System for your server.

Depending on the version, available configuration options may include:

* Discord Bot Token
* Discord Guild ID
* Discord Role IDs
* Discord Webhook
* Countdown duration
* Notification settings
* Other system settings

***

## Step 4 — Configure Discord Bot Token

The `/dvall` permission system uses a Discord bot to verify a player's Discord roles.

Enter your Discord bot token into the appropriate configuration option.

Example:

```
Discord Bot Token = "YOUR_BOT_TOKEN"
```

#### Important

**Never share your Discord bot token publicly.**

Treat your bot token like a password. Anyone with access to the token may be able to control your Discord bot.

***

## Step 5 — Configure Discord Guild ID

Enter the ID of the Discord server where your staff roles are located.

Example:

```
Discord Guild ID = "YOUR_GUILD_ID"
```

Make sure the ID belongs to the correct Discord server.

***

## Step 6 — Configure Staff Role IDs

Add the Discord role IDs that should be authorized to use:

```
/dvall
```

Only users with one of the configured roles should be able to perform a server-wide vehicle wipe.

Example:

```
Staff Roles:
- Administrator
- Moderator
- Management
```

Use the actual Discord role IDs required by the configuration rather than the role names.

***

## Step 7 — Configure The Discord Webhook

If you want vehicle wipes to be logged to Discord, create a webhook in the Discord channel where you want the logs to appear.

Enter the webhook URL into the appropriate configuration option.

Example:

```
Discord Webhook = "YOUR_WEBHOOK_URL"
```

#### Important

Do not post your webhook URL publicly.

***

## Step 8 — Configure The Countdown

Configure the amount of time players should receive before the vehicle wipe begins.

The countdown gives players an opportunity to enter or move their vehicles before the cleanup starts.

Choose a duration appropriate for your server's roleplay environment.

***

## Step 9 — Add The Resource To server.cfg

Open your server's:

```
server.cfg
```

Add the resource to your startup configuration:

```cfg
ensure X1S-AdvDVSystem
```

Make sure the resource name matches the folder name inside your resources directory.

Because the script is standalone, no framework needs to be started before it.

***

## Step 10 — Restart Your Server

Restart your FiveM server after completing the configuration.

You can also start the resource directly from the server console:

```
ensure X1S-AdvDVSystem
```

Check the server console for errors after starting the resource.

***

## Step 11 — Test `/dv`

Join the server and test:

```
/dv
```

Test the command while:

* Inside a vehicle
* Near another vehicle
* Around multiple vehicles

Verify that the intended vehicle is deleted.

***

## Step 12 — Test `/dvall`

Log into the server using an account with an authorized Discord role.

Run:

```
/dvall
```

Verify that:

1. The permission check succeeds.
2. All players receive the countdown.
3. The countdown displays correctly.
4. The vehicle wipe begins.
5. The live vehicle counter appears.
6. Occupied vehicles are protected.
7. Abandoned vehicles are removed.
8. The Discord webhook receives the wipe log.

***

## Step 13 — Test Permissions

Test `/dvall` using an account that does **not** have an authorized Discord role.

The player should receive:

```
No Permissions
```

The vehicle wipe should not begin.

This test is important to ensure regular players cannot trigger a server-wide vehicle cleanup.

***

## Discord Bot Setup

### Create A Discord Application

If you do not already have a Discord bot:

1. Open the Discord Developer Portal.
2. Create a new application.
3. Create a bot for the application.
4. Copy the bot token.
5. Add the bot to your Discord server.

Keep the bot token private.

***

### Bot Permissions

Make sure the Discord bot has the permissions necessary for the role verification system to function correctly.

The bot should be able to access the server and retrieve the required member/role information.

***

## Discord Webhook Setup

To create a webhook:

1. Open the Discord channel where you want vehicle wipe logs.
2. Open the channel settings.
3. Navigate to **Integrations**.
4. Select **Webhooks**.
5. Create a new webhook.
6. Copy the webhook URL.
7. Add the URL to the Advanced DV configuration.

Test the webhook by performing a `/dvall` wipe.

***

## Troubleshooting

### `/dv` Does Not Work

If `/dv` does not delete a vehicle:

* Verify the resource is running.
* Check the server console for errors.
* Verify the resource name in `server.cfg`.
* Restart the resource.
* Make sure you are targeting a valid vehicle.

***

### `/dvall` Says "No Permissions"

If an authorized staff member receives:

```
No Permissions
```

check:

* Discord Bot Token
* Discord Guild ID
* Discord Role ID
* Discord bot membership
* Discord role assignment
* ACE/permission configuration if applicable

Make sure the player is using the Discord account associated with the authorized role.

***

### Discord Role Verification Does Not Work

Verify that:

* The bot is inside your Discord server.
* The Guild ID is correct.
* The configured Role ID is correct.
* The staff member actually has the configured role.
* The bot can access the necessary Discord member information.
* The bot token is valid.

Restart the resource after making configuration changes.

***

### Discord Logs Are Not Sending

If `/dvall` works but no Discord log appears:

* Verify the webhook URL.
* Make sure the webhook still exists.
* Verify the webhook belongs to the intended channel.
* Check the server console for errors.
* Generate a new webhook and test again if necessary.

***

### Occupied Vehicles Are Being Deleted

If vehicles containing players are being removed during `/dvall`:

1. Check the server console for errors.
2. Verify you are running the correct version of the script.
3. Restart the resource.
4. Test the vehicle protection system again.

If the issue persists, open a support ticket with X1Studios.

***

### Countdown Does Not Display

If players do not see the wipe countdown:

* Verify the resource started correctly.
* Check the client console for errors.
* Verify the NUI files are present.
* Restart the resource.
* Reconnect to the server.

***

## Updating The Script

Before updating X1Studios Advanced DV System:

1. Stop the existing resource.
2. Back up your configuration.
3. Download the newest version.
4. Replace the existing resource files.
5. Reapply your configuration if required.
6. Start the resource.
7. Test `/dv`.
8. Test `/dvall`.
9. Test Discord permissions.
10. Test Discord logging.

Always review the release information for the version you are installing.

***

## Installation Complete

The **X1Studios Advanced Delete Vehicle System** is now installed and ready for use.

Players can use:

```
/dv
```

Authorized staff can use:

```
/dvall
```

The system will handle the countdown, vehicle protection, live wipe counter, and Discord integrations automatically.

For support, open a ticket in the official X1Studios Discord.

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
