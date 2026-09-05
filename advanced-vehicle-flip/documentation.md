# Documentation

## X1Studios Advanced Vehicle Flip System

### Overview

The **X1Studios Advanced Vehicle Flip System** is a fully standalone FiveM resource designed to provide a simple, immersive, and balanced way for players to recover overturned vehicles.

Instead of allowing players to exploit vehicle physics or manipulate their wheels from inside the vehicle, players must exit the vehicle and use the `/flipvehicle` command to begin the recovery process.

The system features a modern red-glow notification interface, a live **15-second countdown**, a dedicated flipping animation, and automatic vehicle recovery when the process completes.

***

### Features

#### Vehicle Flipping

Players can easily recover an overturned vehicle by exiting the vehicle and using:

```
/flipvehicle
```

The system handles the vehicle recovery process automatically.

***

#### Anti-Exploit Protection

The system is designed to discourage vehicle wheel-wiggle and similar physics exploits.

Players must:

1. Exit the vehicle.
2. Approach the vehicle.
3. Use `/flipvehicle`.
4. Wait for the recovery timer to complete.

This creates a more controlled and fair vehicle recovery system.

***

#### 15-Second Flip Timer

Vehicle recovery includes a live countdown.

Players will see a notification similar to:

```
Flipping Vehicle - 15s
```

The timer counts down until the process reaches:

```
Flipping Vehicle - 0s
```

Once the countdown is completed, the vehicle is recovered.

If the process is interrupted, the timer can reset.

***

#### Modern Red Notification UI

The system uses a modern notification interface featuring:

* Red glow styling
* Animated notifications
* Smooth slide-in effects
* Live countdown information
* Success feedback
* Failure feedback

The interface is designed to fit modern FiveM roleplay servers.

***

#### Flipping Animation

While recovering a vehicle, the player performs a dedicated animation.

This adds additional immersion instead of instantly correcting the vehicle position.

***

#### Intelligent Feedback

The system provides feedback when the command cannot be completed.

Examples include:

* No nearby vehicle
* Player is inside a vehicle
* Vehicle cannot be flipped
* Flip process interrupted
* Vehicle successfully flipped

***

### How It Works

The vehicle recovery process is simple:

#### Step 1 — Exit Your Vehicle

Players must be outside of the vehicle before attempting to flip it.

#### Step 2 — Approach the Vehicle

Move close to the overturned vehicle.

#### Step 3 — Start the Flip

Use:

```
/flipvehicle
```

#### Step 4 — Flip Timer

The system begins the 15-second recovery countdown.

```
Flipping Vehicle - 15s
```

The timer continues down to zero.

#### Step 5 — Vehicle Recovery

Once the timer reaches zero, the vehicle is automatically righted.

***

### Command

The primary command is:

```
/flipvehicle
```

#### `/flipvehicle`

Attempts to recover a nearby overturned vehicle.

The player must be outside of the vehicle and positioned close enough to interact with it.

***

### Configuration

The system is designed to be customizable for server owners.

Depending on the version of the resource, configurable options may include:

* Flip timer duration
* Notification settings
* UI behavior
* Vehicle interaction settings
* Other resource-specific options

Always use the configuration options included with your version of the resource.

***

### Compatibility

The X1Studios Advanced Vehicle Flip System is:

* **Fully Standalone**
* Framework independent
* Dependency free

It can be used with servers running:

* QBCore
* QBox
* ESX
* vMenu
* Custom frameworks
* Standalone servers

No framework integration is required.

***

### Performance

The system is designed to be lightweight and suitable for everyday use on FiveM servers.

The resource only needs to perform vehicle and player interaction checks when the system is being used, helping minimize unnecessary server/client workload.

***

### Perfect For

The Advanced Vehicle Flip System is ideal for:

* Roleplay servers
* Public FiveM servers
* Racing servers
* Freeroam servers
* Vehicle-focused communities
* Realism-focused servers
* Emergency services roleplay

***

### Why Use The X1Studios Vehicle Flip System?

The system provides a more immersive alternative to traditional vehicle flipping.

Instead of:

```
Vehicle flips → Player wiggles wheels → Vehicle magically recovers
```

The system creates a more realistic interaction:

```
Vehicle flips
      ↓
Player exits vehicle
      ↓
Player approaches vehicle
      ↓
/flipvehicle
      ↓
15-second recovery
      ↓
Vehicle is recovered
```

This makes vehicle recovery feel like an actual gameplay interaction rather than a physics exploit.

***

### Requirements

**Requirements:**

```
Nothing
```

The resource is completely standalone and does not require any external dependencies.

***

### Support

Need help installing or configuring the resource?

Join the **X1Studios Discord** for support, updates, previews, and future releases.

**Discord:**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

Support is available through the X1Studios Discord support system.

***

### X1Studios

X1Studios creates FiveM resources, EUP packs, liveries, scripts, and other custom content designed to improve the experience of FiveM communities.

Join the Discord to see upcoming releases, free resources, previews, and development updates.
