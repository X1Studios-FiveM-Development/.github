# Documentation

## X1Studios Advanced Delete Vehicle System

### Overview

The **X1Studios Advanced Delete Vehicle System** is a lightweight and fully standalone vehicle management system designed to help FiveM servers control abandoned and unwanted vehicles.

The system provides two primary commands:

* `/dv` — Available to all players
* `/dvall` — Staff-only server-wide vehicle wipe

Unlike basic vehicle deletion scripts, the Advanced DV System includes a server-wide countdown, intelligent player vehicle protection, live wipe statistics, modern notifications, Discord role permissions, and Discord logging.

The system is designed to keep vehicle cleanup efficient without unnecessarily disrupting active roleplay.

***

## Commands

### `/dv`

The `/dv` command allows players to delete a vehicle.

Players can use the command to delete:

* The vehicle they are currently inside
* A nearby vehicle

This provides players with a simple way to remove unwanted vehicles without requiring staff assistance.

***

### `/dvall`

The `/dvall` command is a **staff-only** command designed to perform a server-wide vehicle cleanup.

When `/dvall` is executed:

1. Staff permissions are verified.
2. All players receive a countdown notification.
3. Players are given time to enter their vehicles.
4. The vehicle cleanup begins.
5. Vehicles containing players are protected.
6. A live counter displays the number of vehicles removed.
7. The completed wipe is logged to Discord.

***

## Features

### Discord Role Permissions

The `/dvall` command uses Discord role verification to restrict access to authorized staff.

The system can verify a player's Discord roles using:

* Discord Bot Token
* Discord Guild ID
* Configured Discord Role IDs

Only players with an approved role can execute the server-wide vehicle wipe.

This prevents regular players from accidentally or intentionally triggering a full vehicle cleanup.

***

## Server-Wide Countdown

Before a `/dvall` vehicle wipe begins, all players receive a visible countdown warning.

This gives players an opportunity to:

* Enter their vehicle
* Move their vehicle
* Prepare for the cleanup
* Avoid having an abandoned vehicle removed

The countdown helps prevent unexpected vehicle deletion during active roleplay.

***

## Vehicle Protection

The Advanced DV System intelligently protects vehicles that players are currently occupying.

During a server-wide wipe, the system checks vehicles before deleting them.

#### Protected Vehicles

A vehicle will not be deleted if a player is currently inside it.

This helps ensure active roleplay vehicles are not accidentally removed during a server-wide cleanup.

***

## Live Vehicle Wipe Counter

During a `/dvall` wipe, players receive a live counter displaying the number of vehicles that have been removed.

The counter updates as the cleanup progresses.

This gives players a clear indication that the vehicle wipe is actively running.

***

## Modern Notification UI

The system uses a modern red notification interface for system messages.

Notifications can inform players about:

* Vehicle deletion
* Wipe countdowns
* Wipe activity
* Permission errors
* Other system messages

The notification system avoids unnecessary chat spam and keeps important information visible on screen.

***

## Permission Feedback

Players who attempt to use `/dvall` without the required permissions receive an on-screen notification.

The default permission message is:

```
No Permissions
```

This makes it immediately clear that the player does not have access to the server-wide vehicle wipe.

***

## Discord Webhook Logging

Server-wide vehicle wipes can be logged to Discord using a webhook.

The log records information about the staff member who triggered the wipe.

This gives server management a record of when vehicle wipes occurred and who initiated them.

***

## Standalone

The Advanced DV System is completely standalone.

It does not require:

* QBCore
* QBox
* ESX
* ox\_lib
* Any other framework

The script can be used on virtually any FiveM server configuration.

***

## Performance

The script was designed to remain lightweight while handling large vehicle cleanup operations.

Vehicle scanning and deletion are handled efficiently to minimize unnecessary performance impact.

This makes the system suitable for:

* Small servers
* Medium-sized servers
* High-player-count servers
* Servers with significant vehicle buildup

***

## Perfect For

The Advanced DV System is ideal for:

* Roleplay servers
* Economy servers
* Public FiveM communities
* Large FiveM servers
* Servers with abandoned vehicle buildup
* Servers requiring staff-controlled vehicle cleanup

***

## Requirements

The script is standalone, but Discord functionality requires the following:

* FiveM server
* Discord Bot Token
* Discord Guild ID
* Discord Role IDs
* Discord Webhook URL for logging

No FiveM framework is required.

***

## How The System Works

#### Player Vehicle Deletion

A player uses:

```
/dv
```

The system identifies the player's current or nearby vehicle and removes it.

#### Staff Vehicle Wipe

A staff member uses:

```
/dvall
```

The system:

**1.** Verifies Discord permissions.

**2.** Announces the upcoming vehicle wipe.

**3.** Starts the countdown.

**4.** Scans vehicles across the server.

**5.** Protects vehicles containing players.

**6.** Deletes eligible abandoned vehicles.

**7.** Updates the live vehicle counter.

**8.** Logs the wipe to Discord.

***

## Support

For support with the X1Studios Advanced DV System, open a support ticket in the official X1Studios Discord.

**Support is provided through Discord tickets only.**

#### X1Studios Discord

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

***

## Community

Join the X1Studios Discord for:

* Upcoming script previews
* Free FiveM EUP packs
* Liveries
* Scripts
* Development updates
* New releases
* Support

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
