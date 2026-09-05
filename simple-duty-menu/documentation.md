# Documentation

## X1Studios Simple Duty System

> **Deprecated Resource**
>
> This script is **deprecated and no longer receives updates or active development**. It may still be used on compatible FiveM servers, but future compatibility or bug fixes are not guaranteed.

The **X1Studios Simple Duty System** is a lightweight standalone duty management system designed for FiveM servers that need a simple way for multiple departments to go on and off duty.

The system uses **OX\_Lib** for its duty menu and provides department management, custom names and callsigns, duty blips, Discord permission integration, Discord webhook logging, and chat-based notifications.

### Features

#### Multiple Departments

Create and manage multiple departments through the resource configuration.

Each department can have its own:

* Department name
* Callsign configuration
* Duty settings
* Blip settings
* Permissions

The system is designed to support additional departments beyond the default configuration.

#### Discord ACE Permissions Using Roles

The duty system supports **Discord-based ACE permissions**, allowing access to be controlled through Discord roles.

This allows server administrators to restrict duty access to authorized members without relying exclusively on in-game permission groups.

#### Discord Webhook Logging

Duty activity can be logged directly to Discord using a webhook.

This can be used to track when authorized members:

* Go on duty
* Go off duty
* Change their duty status

Logs provide server staff with an easy way to monitor department activity.

#### Custom Names & Callsigns

Players can use configurable names and callsigns within the duty system.

This allows departments to maintain their own naming and callsign structure.

#### Duty Blips

The system provides duty-related map blips for players who are on duty.

This can help members of a department identify active personnel while they are operating within the server.

#### OX\_Lib Menu

The duty menu is powered by **OX\_Lib**, providing a lightweight and familiar interface for managing duty status.

OX\_Lib handles the menu interaction while the duty system manages the underlying department and player status.

#### Chat Notifications

The script uses FiveM's **Chat** resource for duty notifications.

Players receive notifications through chat when performing supported duty actions.

#### Duty Command

The primary command for opening the duty system is:

```
/dutymenu
```

The command opens the OX\_Lib duty menu, allowing authorized users to manage their duty status.

### How It Works

The general duty workflow is:

1. An authorized player uses `/dutymenu`.
2. The OX\_Lib menu opens.
3. The player selects the appropriate department or duty option.
4. Their duty status is updated.
5. The appropriate notification is displayed through chat.
6. Duty information and blip status are updated.
7. The activity can be logged through the configured Discord webhook.

### Configuration

The resource includes configuration options for managing the available departments and system behavior.

Depending on the resource configuration, administrators can customize items such as:

* Departments
* Department names
* Callsigns
* Duty blips
* Permissions
* Discord logging
* Webhook settings
* Other available resource settings

Refer to the included configuration files for the exact options available in your version of the resource.

### Requirements

The following resources are required:

#### OX\_Lib

OX\_Lib is required for the duty menu.

**Required Resource:**

```
ox_lib
```

#### Chat

The FiveM Chat resource is required for duty notifications.

**Required Resource:**

```
chat
```

### Compatibility

The script was designed as a lightweight FiveM duty system and does not require a specific framework.

It can be used for servers that need a simple department-based duty system without implementing a large framework-dependent system.

Because the resource is **deprecated**, compatibility with newer FiveM artifacts, resources, or dependencies is not guaranteed.

### Performance

The Simple Duty System is designed to remain lightweight and only handles the functionality required for department duty management.

Its primary systems include:

* Duty status management
* Department management
* Duty blips
* Permission checks
* Discord logging
* Menu interactions
* Chat notifications

### Deprecated Status

This resource is officially **deprecated**.

That means:

* No new features are being developed.
* No regular updates are being released.
* Compatibility with future FiveM updates is not guaranteed.
* Bugs discovered after deprecation may not be fixed.
* New X1Studios resources may replace or supersede this system.

If you are starting a new server project, it is recommended to use a newer X1Studios duty resource when available.

### Support & Community

Although this resource is deprecated, the X1Studios community remains available for general support and assistance.

Join the official X1Studios Discord for:

* Support
* Upcoming scripts
* FiveM EUP packs
* Custom liveries
* Development updates
* Previews of upcoming releases

**Discord:**\
[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
