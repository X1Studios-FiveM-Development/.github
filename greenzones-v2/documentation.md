# Documentation

## X1Studios GreenZone System v2

### Overview

**X1S-GreenZones** is a lightweight and configurable FiveM GreenZone system designed to create protected areas throughout your server.

Using **ACE Permissions** and **PolyZone**, server owners can create and manage multiple protected areas while maintaining complete control over who can access the GreenZone management system.

The included **Custom Admin UI** makes managing zones simple without requiring server owners to manually edit configuration files for every zone.

***

## Features

### Protected GreenZones

Create designated protected areas throughout your server.

GreenZones can be used to establish controlled areas where specific player actions can be restricted or disabled.

Perfect for locations such as:

* Civilian safe zones
* Police facilities
* Government buildings
* Fire and EMS stations
* Spawn locations
* Businesses
* Event areas
* Custom RP locations

***

### ACE Permission Support

X1S-GreenZones uses **ACE Permissions** to control access to the GreenZone management system.

Server owners can determine which players or staff members are allowed to manage GreenZones.

This allows your server to maintain control over administrative functionality without requiring a framework.

***

### PolyZone Integration

The system uses **PolyZone** for zone detection.

This allows server owners to create accurate custom-shaped zones rather than being limited to simple circular areas.

PolyZone provides the foundation for detecting when players enter and leave configured GreenZones.

***

### Custom Admin UI

X1S-GreenZones includes a modern in-game administration interface.

Authorized administrators can manage GreenZones without manually editing configuration files.

The admin interface can be used to:

* Create zones
* Edit zones
* Manage existing zones
* Remove zones
* Configure individual zones

Access to the management interface is controlled through ACE Permissions.

***

### Multiple GreenZones

Create and manage multiple protected areas throughout your server.

Each GreenZone can be configured independently, allowing different locations to have different settings.

For example:

```
Police Station
    ↓
GreenZone

Fire Station
    ↓
GreenZone

Civilian Spawn
    ↓
GreenZone

Business
    ↓
GreenZone
```

***

### Custom Notifications

Players can receive notifications when entering or leaving a GreenZone.

This provides immediate feedback and helps players understand when they have entered or exited a protected area.

Notifications can be configured according to the options provided by the resource.

***

### Performance Optimized

X1S-GreenZones is designed to remain lightweight while continuously detecting player zone status.

The system uses PolyZone-based detection to determine when players enter or leave protected areas without unnecessarily consuming server resources.

***

## Admin Management

GreenZone management is restricted through **ACE Permissions**.

Authorized users can access the custom administration interface and manage the zones available on the server.

This allows server owners to separate normal player access from administrative GreenZone management.

***

## GreenZone Workflow

The basic workflow is:

```
Administrator
      ↓
ACE Permission Check
      ↓
Open GreenZone Admin UI
      ↓
Create / Edit / Manage Zone
      ↓
PolyZone Detection
      ↓
Player Enters Zone
      ↓
GreenZone Restrictions Apply
      ↓
Player Receives Notification
```

When the player leaves the zone, the system detects the change and provides the appropriate notification.

***

## Perfect For

X1S-GreenZones can be used for many different types of FiveM servers and locations.

#### Civilian Safe Zones

Create protected areas where civilians can safely interact.

#### Police & Government Facilities

Protect law enforcement and government facilities.

#### Fire & EMS Stations

Create protected areas around emergency service locations.

#### Spawn Areas

Protect new players immediately after spawning.

#### Businesses

Create protected areas around player-owned or server-owned businesses.

#### Event Areas

Protect event locations from unwanted interactions.

#### Custom RP Locations

Create GreenZones anywhere on your map for your server's specific roleplay needs.

***

## Compatibility

X1S-GreenZones is designed to work independently of your server framework.

Compatible with:

* Standalone servers
* QBCore
* QBox
* ESX
* vMenu
* Custom frameworks

No framework is required.

***

## Requirements

The primary requirement is:

#### PolyZone

**PolyZone GitHub:**

[https://github.com/mkafrin/PolyZone](https://github.com/mkafrin/PolyZone)

ACE Permissions are handled through FiveM and do not require an additional framework.

***

## Standalone

X1S-GreenZones is fully standalone.

It does not require:

* QBCore
* QBox
* ESX
* ox\_lib
* vMenu
* Any economy framework

The only external resource requirement is **PolyZone**.

***

## Performance

The system was designed with performance in mind.

GreenZones continuously monitor player locations while keeping resource usage lightweight.

This makes it suitable for servers with multiple active GreenZones.

***

## Why Use X1S-GreenZones?

X1S-GreenZones combines:

* ACE permission management
* PolyZone detection
* Multiple protected areas
* Custom GreenZone administration
* Modern admin UI
* Player notifications
* Standalone functionality
* Performance-focused design

Instead of manually managing every zone through configuration files, authorized administrators can manage their GreenZones directly through the included administration interface.

***

## Support & Community

Want to see upcoming **X1Studios releases, previews, free FiveM EUP packs, liveries, scripts**, and more?

Join the official X1Studios Discord:

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

***

## Support

**SUPPORT — YES | DISCORD TICKETS ONLY**

For support, please open a ticket in the X1Studios Discord.

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

**X1Studios — FiveM Development & Resources**
