# Documentation

## X1Studios Advanced Duty System

### Advanced Duty System for FiveM

The **X1Studios Advanced Duty System** is a fully standalone FiveM duty management system designed for roleplay communities with multiple departments. It provides an easy-to-use duty menu, department management, Discord integration, duty blips, supervisor controls, 911 calls, panic alerts, and more.

The system requires **no external resources or frameworks** and can be configured to fit your server's departments, ranks, callsigns, permissions, and Discord setup.

***

### Features

#### Fully Standalone

The X1Studios Advanced Duty System does not require ESX, QBCore, Qbox, or any other framework.

**Requirements:**

* FiveM Server
* Nothing else

***

#### Discord Ace Permissions

The system supports Discord-based ACE permissions, allowing you to control access using Discord roles.

Permissions can be configured for:

* Duty System
* Supervisor Panel
* Department access
* Supervisor actions
* Other restricted features

This allows server staff to manage permissions directly through Discord roles without having to manually assign permissions to individual players.

***

#### Multiple Departments

Create and configure multiple departments through the configuration.

Examples include:

* Blaine County Sheriff's Office
* Los Santos Police Department
* San Andreas State Troopers
* Fire Department
* EMS
* Game Wardens
* Communications
* Custom Departments

Each department can have its own:

* Name
* Callsigns
* Ranks
* Duty settings
* Blip settings
* Permissions

You can create as many departments as your server requires.

***

#### Custom Names, Callsigns & Ranks

The system allows departments to use custom personnel information.

Configure:

* Officer name
* Callsign
* Rank
* Department
* Other personnel information

This information can be displayed throughout the duty system and used for dispatch and logging.

***

## Commands

### `/dutymenu`

Opens the Advanced Duty System menu.

From the duty menu, authorized users can manage their duty status and access available department options.

**Command:**

```
/dutymenu
```

***

### `/offduty`

Allows an on-duty member to go off duty.

**Command:**

```
/offduty
```

Going off duty will remove the player from active duty systems, including duty-related tracking and notifications.

***

### `/supervisormenu`

Opens the Supervisor Panel for authorized supervisors.

**Command:**

```
/supervisormenu
```

The Supervisor Panel is restricted using the configured supervisor permissions.

***

## Supervisor Panel

The Supervisor Panel allows authorized supervisors to manage personnel currently on duty.

#### Force Off Duty

Supervisors can select an active employee and force them off duty.

This can be useful when:

* An officer forgets to go off duty
* A supervisor needs to remove someone from duty
* A player is AFK while still marked on duty
* Administrative action is required

Supervisor permissions are controlled through the configuration.

***

## Duty Blips

The Advanced Duty System includes an integrated duty blip system.

When personnel go on duty, their configured duty blip can appear on the map.

Duty blips can be configured based on the department and can help supervisors and other authorized personnel keep track of active units.

The system also handles duty status changes to ensure blips are properly created and removed.

***

## Notifications

The system includes a built-in notification system for important events.

Notifications can be used for:

* Going on duty
* Going off duty
* 911 calls
* Panic alerts
* Duty status changes
* Supervisor actions
* Other system events

The notification system was completely revamped in **v1.6.1**.

***

## Discord Webhook Logging

The system supports Discord webhook logging for important duty-related events.

Logs can be sent to a configured Discord webhook for administrative tracking.

Depending on the event, logs can include information such as:

* Player name
* Player ID
* Department
* Callsign
* Rank
* Duty status
* Event type
* Timestamp

This gives server administrators an easy way to monitor department activity.

***

## 911 Call System

Introduced in **v1.1.0**, the integrated 911 system allows players to send emergency calls directly to on-duty personnel.

#### Sending a 911 Call

Players can use:

```
/911
```

The system allows the caller to provide information about the emergency.

Once submitted, the call is dispatched to **on-duty officers only**.

***

### 911 Officer Notifications

When a 911 call is received, all eligible on-duty officers are notified.

Off-duty personnel will not receive the call.

This keeps emergency dispatch information limited to active units.

***

### 911 Location Blip

911 calls generate a map blip at the reported location.

Officers can use the blip to locate the emergency and respond appropriately.

The 911 blip system was updated in **v1.2.0** with improved functionality.

***

### 911 Discord Webhook

911 calls can also be sent to a configured Discord webhook.

The webhook can be configured to **ping a specific Discord role**, allowing departments to receive immediate notifications in Discord when a 911 call is received.

Example:

```
@Police
New 911 Call Received
Location: Davis
Reason: Suspicious Person
```

The exact format depends on your configuration.

***

## Panic System

Introduced in **v1.2.0**, the Panic System provides officers with an emergency alert system.

When activated, the panic alert can notify other active personnel that an officer requires immediate assistance.

#### Panic Alert

The panic alert can be displayed through the system's notification/chat system.

Active personnel can receive:

* Panic notification
* Officer information
* Location information
* Map blip

***

### Panic Blip

A panic activation creates a map blip at the officer's location.

This allows responding personnel to quickly identify where assistance is needed.

The panic system is designed for high-priority emergency situations.

***

## Disconnect Off-Duty Logging

Starting with **v1.2.0**, the system includes disconnect logging.

If a player disconnects while on duty, the system can record the event through Discord logging.

This helps supervisors identify personnel who leave the server while still marked as active.

***

## Version History

### v1.0.0

Initial release featuring:

* Fully standalone system
* Discord ACE permissions
* Discord webhook logging
* Multiple department support
* Custom department names
* Custom callsigns
* Custom ranks
* Chat notifications
* Duty blips
* `/dutymenu`
* `/offduty`
* `/supervisormenu`
* Supervisor force-off-duty functionality

***

### v1.1.0

#### 911 Update

Added:

* 911 call system
* 911 calls sent to on-duty officers only
* 911 location blips
* 911 Discord webhook
* Discord role ping support

***

### v1.2.0

#### Emergency Systems Update

Added:

* Panic system
* Panic alerts
* Panic map blips
* Disconnect off-duty logging
* Updated 911 call blips

***

### v1.6.1

#### Major System Overhaul

Added:

* Completely revamped UI
* Fully reworked duty system
* New notification system
* Fixed duty blips
* Improved system functionality
* Numerous additional improvements and fixes

***

## Support

Need help installing, configuring, or troubleshooting the X1Studios Advanced Duty System?

Join the official **X1Studios Discord** for support, development updates, previews, and announcements.

**X1Studios Discord:**\
[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

You can also find previews of upcoming:

* Free FiveM EUP Packs
* Liveries
* Scripts
* Development projects
* Updates

***

## Showcase

Watch the latest showcase of the X1Studios Advanced Duty System:

**YouTube Showcase:**\
[https://youtu.be/ZLFCtq778-w?si=7SOEn7EqV6JcfTk](https://youtu.be/ZLFCtq778-w?si=7SOEn7EqV6JcfTk)\_

***

## Credits

**Developer:** X1Studios - Havoc Sheriff

**Script:** X1Studios Advanced Duty System

**Latest Version:** v1.6.1

**Framework:** Standalone

**Dependencies:** None
