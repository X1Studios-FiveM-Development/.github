# Documentation

X1S Life System is a standalone FiveM resource that covers a player's whole session, from first join to patrol. It includes:

* Character creation and selection
* A spawn selector
* Duty management
* 911 and panic dispatch
* A full CAD/MDT
* Robberies
* Physical ID and license cards

It does not require ESX, QBCore, Qbox, or vRP. The only dependency is `oxmysql`, which is used purely as a database driver.

***

### Quick Start

1. Install `oxmysql` and make sure it is working.
2. Copy `X1S-LifeSystem` into your `resources` folder.
3. Import `sql/database.sql` into your database.
4. Add your Discord bot token, guild ID, role IDs, and webhooks (see Discord Setup).
5. Add both resources to `server.cfg`, `oxmysql` first.
6. Restart the server.

***

### Requirements

| Requirement                          | Notes                                                                                        |
| ------------------------------------ | -------------------------------------------------------------------------------------------- |
| `oxmysql`                            | Must start **before** X1S-LifeSystem                                                         |
| MySQL / MariaDB database             | Stores characters, vehicles, warrants, arrests, citations, incidents, and CAD reference data |
| A Discord server and bot             | Used for duty role verification and logging                                                  |
| Players with Discord linked to FiveM | Role checks read each player's Discord identifier                                            |
| FiveM artifact with Lua 5.4          | The resource uses `lua54 'yes'`                                                              |

***

### Installation

#### 1. Add the resource

Copy the `X1S-LifeSystem` folder into your server's `resources` directory.

#### 2. Import the database

Import `sql/database.sql` into the database your oxmysql connection string points to. This creates the following tables:

| Table                 | Purpose                              |
| --------------------- | ------------------------------------ |
| `x1s_characters`      | Player characters and license status |
| `x1s_vehicles`        | Registered vehicles                  |
| `x1s_vehicle_history` | Vehicle change history               |
| `x1s_vehicle_bolos`   | Vehicle BOLOs                        |
| `x1s_warrants`        | Warrants                             |
| `x1s_arrests`         | Arrest records                       |
| `x1s_citations`       | Citation records                     |
| `x1s_incidents`       | Incident reports                     |
| `x1s_ten_codes`       | Editable 10-code list                |
| `x1s_penal_codes`     | Editable penal code list             |

The 10-codes and penal codes are seeded from `config.lua` on first start, once the tables are empty. After that, they are managed in-game from the CAD Admin tab.

If you are upgrading an existing database, run the migration statements at the bottom of `sql/database.sql` once. They add the `brand` column to vehicles and the `address` column to characters. Fresh installs already include them.

#### 3. Configure Discord

See Discord Setup below.

#### 4. Update `server.cfg`

cfg

```cfg
ensure oxmysql
ensure X1S-LifeSystem
```

`oxmysql` must be listed above X1S-LifeSystem. When the resource starts, the console reports whether the database connection is working.

***

### Discord Setup

Duty verification, supervisor permissions, and CAD admin permissions are all based on Discord roles. The resource asks Discord whether a player's account holds the required role each time it needs to check.

#### Bot requirements

* Create a Discord bot and add it to your server.
* The bot must be able to view server members.
* Every player who goes on duty must have Discord open and linked to FiveM.

#### Where to put your values

You can enter values in either of two places. Convars are recommended because they keep secrets out of the resource folder.

**Option A: `server.cfg` convars (recommended)**

Use `set`, not `setr`. `setr` replicates the value to players.

cfg

```cfg
set x1s_bot_token "YOUR_BOT_TOKEN"
set x1s_guild_id "YOUR_GUILD_ID"
set x1s_leo_role_id "YOUR_LEO_ROLE_ID"
set x1s_admin_role_id "YOUR_ADMIN_ROLE_ID"

set x1s_lspd_duty_role "ROLE_ID"
set x1s_lspd_supervisor_role "ROLE_ID"
```

**Option B: edit `server_config.lua` directly**

Each value is written as `GetConvar('name', 'fallback')`. If no convar is set, the fallback typed in the file is used.

> **Never share your bot token or webhook URLs.** Do not post `server_config.lua` publicly or commit it with real values. If a token or webhook is ever exposed, regenerate it in Discord.

#### Convar reference

| Setting                    | Convar                       | Purpose                                                 |
| -------------------------- | ---------------------------- | ------------------------------------------------------- |
| Bot token                  | `x1s_bot_token`              | Authenticates the bot with Discord                      |
| Guild ID                   | `x1s_guild_id`               | Your Discord server ID                                  |
| LEO role                   | `x1s_leo_role_id`            | Role pinged on 911 calls                                |
| Admin role                 | `x1s_admin_role_id`          | Unlocks the CAD Admin tab and record deletion           |
| Department duty role       | `x1s_<dept>_duty_role`       | Required to go on duty in that department               |
| Department supervisor role | `x1s_<dept>_supervisor_role` | Allows force-off and panic clearing for that department |
| Department webhook         | `x1s_<dept>_webhook`         | Duty logs for that department                           |
| Dispatch webhook           | `x1s_dispatch_webhook`       | 911 call logs                                           |
| Panic webhook              | `x1s_panic_webhook`          | Panic alert logs                                        |

`<dept>` is the lowercase department key, for example `lspd`, `bcso`, `sast`, or `sagw`.

#### Log webhooks

Each of these has its own convar in the form `x1s_log_<name>_webhook`. You can point them all at one channel or split them up.

| Log event                  | Convar                                 |
| -------------------------- | -------------------------------------- |
| Character created          | `x1s_log_character_created_webhook`    |
| Character deleted          | `x1s_log_character_deleted_webhook`    |
| Player spawn               | `x1s_log_player_spawn_webhook`         |
| Citation issued            | `x1s_log_citation_webhook`             |
| Arrest made                | `x1s_log_arrest_webhook`               |
| Warrant created            | `x1s_log_warrant_created_webhook`      |
| Warrant closed             | `x1s_log_warrant_closed_webhook`       |
| Vehicle BOLO created       | `x1s_log_vehicle_bolo_created_webhook` |
| Vehicle BOLO closed        | `x1s_log_vehicle_bolo_closed_webhook`  |
| Vehicle registered         | `x1s_log_vehicle_registered_webhook`   |
| Vehicle stolen toggled     | `x1s_log_vehicle_stolen_webhook`       |
| Registration renewed       | `x1s_log_vehicle_renewed_webhook`      |
| Ownership transferred      | `x1s_log_vehicle_transferred_webhook`  |
| Vehicle retired toggled    | `x1s_log_vehicle_retired_webhook`      |
| Citizen notes updated      | `x1s_log_citizen_notes_webhook`        |
| Citizen license updated    | `x1s_log_citizen_license_webhook`      |
| Citizen flags updated      | `x1s_log_citizen_flags_webhook`        |
| Incident created           | `x1s_log_incident_webhook`             |
| CAD reference data changed | `x1s_log_cad_admin_webhook`            |
| CAD record deleted         | `x1s_log_cad_record_deleted_webhook`   |

#### Leaving a value unconfigured

Any value that is empty or contains `_HERE` is treated as not configured. If the bot token or guild ID is unset, the console prints a warning and **duty role checks are denied**, so nobody can go on duty until Discord is set up.

***

### Player Flow

```
New player   →  Character Creator → Character Selector → Spawn Selector → World
Returning    →                      Character Selector → Spawn Selector → World
```

The creator and selector appear over a frozen backdrop with a scripted close-up camera (`Config.Character.creatorCoords`). The resource lets FiveM spawn the ped somewhere hidden, then takes over before the player sees the world.

***

### Commands and Keybinds

#### Commands

| Command                  | Who can use it                               | What it does                                         |
| ------------------------ | -------------------------------------------- | ---------------------------------------------------- |
| `/switchcharacter`       | Anyone in the world                          | Reopens the character flow                           |
| `/spawnselector`         | Anyone with a character loaded               | Reopens the spawn picker                             |
| `/dutymenu`              | Anyone not already on duty                   | Opens the duty menu                                  |
| `/offduty`               | On-duty players                              | Goes off duty                                        |
| `/supervisormenu`        | Discord supervisor role                      | Opens the supervisor menu to force officers off duty |
| `/911`                   | Anyone                                       | Files an emergency report                            |
| `/911calls`              | On-duty officers                             | Views and dismisses the active call queue            |
| `/panic`                 | On-duty officers                             | Sends a silent panic alert to all on-duty officers   |
| `/cad`                   | On-duty officers in a CAD-enabled department | Opens the CAD/MDT                                    |
| `/registervehicle`       | Anyone with a character loaded               | Registers one of your own vehicles                   |
| `/handid`                | Anyone with a character loaded               | Shows your state ID to nearby players                |
| `/handdriverlicense`     | Holder of a valid license                    | Shows that license card to nearby players            |
| `/handmotorcyclelicense` | Holder of a valid license                    | Shows that license card to nearby players            |
| `/handcdl`               | Holder of a valid license                    | Shows that license card to nearby players            |
| `/handweaponlicense`     | Holder of a valid license                    | Shows that license card to nearby players            |
| `/handhuntinglicense`    | Holder of a valid license                    | Shows that license card to nearby players            |
| `/handboatinglicense`    | Holder of a valid license                    | Shows that license card to nearby players            |
| `/handpilotlicense`      | Holder of a valid license                    | Shows that license card to nearby players            |

#### Keybinds

| Default key                 | Action                                 |
| --------------------------- | -------------------------------------- |
| **F6**                      | Open the CAD/MDT                       |
| **P**                       | 911 alert: dismiss                     |
| **K**                       | 911 alert: view in tablet              |
| **Z**                       | 911 alert: respond                     |
| **I**                       | 911 alert: expand                      |
| **Backspace** or **Escape** | Dismiss a displayed ID or license card |

The CAD and 911 alert keys are registered with `RegisterKeyMapping`, so players can rebind them in **Settings → Key Bindings → FiveM**.

***

### Features

#### Character System

* Players can hold up to `Config.Character.maxCharacters` characters (default 5).
* Each character has a name, date of birth, gender (male or female freemode model), and height.
* Age limits (`minAge` and `maxAge`) and height limits (`minHeight` and `maxHeight`) are configurable.
* Deleting characters can be turned off with `allowDelete = false`.
* Each character gets a public state ID (for example `X1S-00042`).

The creator handles **identity only**. Appearance and clothing are left to whichever separate appearance or clothing resource your server uses.

#### Spawn Selector

* Shown automatically after selecting a character, and reopenable with `/spawnselector`.
* The first open is mandatory. Later manual opens can be closed with **Esc** when `Config.Spawn.allowManualClose = true`.
* The loading screen lasts `Config.Spawn.loadingDuration` milliseconds (default 20000).
* Eight locations ship by default. Each entry has a name, district, coordinates, and screenshot in `html/images/`.

To add a spawn location, add an entry to `Config.Spawn.locations` and drop its image into `html/images/`:

lua

```lua
{ name = 'Legion Square', district = 'Downtown Los Santos',
  coords = vector4(223.5, -867.02, 30.49, 11.52), image = 'images/legion.png' },
```

#### Menu Music

A looping ambient track plays on the character creator, character selector, and spawn selector. It keeps playing across all three without restarting. A small control in the top-right corner lets players mute the music or change its volume.

* The track is `html/sound/menu-ambient.mp3`. To change it, replace the file or point the `<audio>` tag in `html/index.html` at your own file. MP3 or OGG will work.
* Music volume, master volume, and UI volume are saved per player.
* If the game blocks autoplay, the music starts on the player's first click.

#### Duty System

1. The player runs `/dutymenu`.
2. They pick a department and enter their name, callsign, and rank. The name is pre-filled from their active character.
3. The resource checks the department's duty role in Discord.
4. If they hold the role, they go on duty and appear on the department roster with a map blip.

If a character is loaded when going on duty, its ID is attached quietly so CAD records can link back to the citizen's profile. Officers without a character can still go on duty, but their records will not have a clickable citizen link.

**Supervisors** (holders of a department's supervisor role) can use `/supervisormenu` to force officers off duty and clear panic alerts for their department.

#### 911 and Panic

* `/911` opens a report form. The report length limit is `Config.Emergency.reportMaxLength` (default 256).
* Reports are automatically ranked **high**, **medium**, or **low** priority by matching keywords, configured in `Config.Emergency.priorityKeywords`. Anything with no match uses `defaultPriority`.
* On-duty officers get a call alert with a map blip. Officers can respond, dismiss, or open the call in the CAD.
* `/911calls` shows the active queue.
* `/panic` sends a silent alert to all on-duty officers and logs it to the panic webhook.

Active 911 calls are held in memory for speed. The queue clears when the resource restarts.

#### Automatic 911 Dispatch

Four in-game actions raise a 911 call automatically. Detection happens on the client, and the server validates it and applies its own cooldown.

| Trigger              | Default priority | Default cooldown |
| -------------------- | ---------------- | ---------------- |
| Carjacking           | High             | None             |
| Shots fired          | High             | 45s              |
| Gun pulled in public | Medium           | 60s              |
| Fight in progress    | Medium           | 45s              |

Each trigger can be enabled or disabled, and its priority, cooldown, and on-duty exemption can be changed under `Config.AutoDispatch`. A gun-pulled call only fires when a living NPC is nearby (`npcRadius`, default 15 meters), and can ignore interiors and specific zones.

#### CAD / MDT

Open with **F6** or `/cad`. Access requires being on duty in a department where `cad = true` and which is listed in `Config.CAD.accessDepartments`.

| Section       | What it does                                                                  |
| ------------- | ----------------------------------------------------------------------------- |
| Home          | Overview, status, and active calls                                            |
| Roster        | On-duty officers and their statuses                                           |
| Citizens      | Search citizens and view profiles, notes, licenses, and flags                 |
| Vehicles      | Search plates, register vehicles, renew, transfer, and mark stolen or retired |
| Warrants      | Create and close warrants with duration presets                               |
| Vehicle BOLOs | Create and close BOLOs with a priority level                                  |
| Incidents     | Create and update incident reports                                            |
| Dispatch      | Live 911 queue with accept, leave, and complete actions                       |
| Panic         | Active panic alerts                                                           |
| 10-Codes      | Reference list                                                                |
| Penal Codes   | Reference list                                                                |
| Admin         | Edit 10-codes and penal codes, delete records (Discord admin role only)       |

**Filing records.** Officers can file citations and arrests directly from a citizen's profile using the charge list. Fine and jail limits come from `Config.CAD`:

| Setting                             | Default           |
| ----------------------------------- | ----------------- |
| `citationMaxFine`                   | 50000             |
| `citationLineMaxFine`               | 10000             |
| `arrestChargeMaxFine`               | 100000            |
| `arrestChargeMaxJailMinutes`        | 1440              |
| `warrantDefaultDurationDays`        | 30                |
| `warrantDurationPresets`            | 7, 14, 30, 60, 90 |
| `vehicleRegistrationRenewalPresets` | 30, 90, 180, 365  |

**Officer statuses** (Active, Busy, On Scene, En Route, Out of Service) and **BOLO priorities** (Routine, Priority, Armed & Dangerous) are set in `Config.CAD.statuses` and `Config.CAD.vehicleBoloPriorities`.

**Charges.** `Config.CAD.charges` is the base charge list. Penal codes are merged in automatically using `Config.CAD.PenalChargeIntegration` (`fineMultiplier`, `jailMinutesDivisor`, and `jailMinutesCap`). A penal code is only citable if its type is Misdemeanor.

**Admin tab.** Shown only to holders of the Discord admin role. Permissions are re-checked on the server for every admin action.

**Tablet animation.** While the CAD, duty, or vehicle registration menus are open, the player holds a tablet. Turn this off with `Config.TabletAnim.enabled = false`.

#### Vehicle Registration

Civilians run `/registervehicle` to register a vehicle by brand, type, color, and plate. The owner is always their active character. Registrations are immediately searchable in the CAD. Officers can also register vehicles manually from the CAD.

Limits are under `Config.VehicleRegistration`:

| Setting                               | Default  |
| ------------------------------------- | -------- |
| `maxOwnedVehicles`                    | 100      |
| `plateMinLength` and `plateMaxLength` | 2 and 16 |
| `registrationValidDays`               | 365      |

#### ID and License Cards

`/handid` and one command per license display a card on the middle-right of the screen for you **and** every in-world player within `Config.IDCards.radius` (default 3.0 game units). It never takes focus, so nobody is blocked from moving or chatting. Dismiss it with **Backspace** or **Escape**.

* Trying to show a license you do not hold in `valid` status is rejected with a notification.
* The photo box uses a male or female silhouette. There is no mugshot capture.
* Hair color, eye color, and weight are generated from the character's ID and are cosmetic only.
* Issue and expiration dates are estimated from the character creation date plus `Config.IDCards.validityYears` (default 5).
* The address line is omitted until something writes to the `address` column of `x1s_characters`.

Licenses are defined in `Config.Character.Licenses`. Each entry has a key, label, command, card title, and card colors. To add a license, add an entry with a `command` value.

#### Robberies

Fourteen locations ship by default: 4 banks, 5 ATMs, and 5 stores. Each has a map blip, a marker prompt, and its own cooldown.

| Type   | Mechanic                                                   |
| ------ | ---------------------------------------------------------- |
| Banks  | Fingerprint hack, 5 rings, 3 mistakes allowed, 55s timeout |
| ATMs   | Fingerprint hack, 3 rings, 3 mistakes allowed, 35s timeout |
| Stores | Progress bar, 22 seconds                                   |

**Controls:** **E** to interact, **Space** to hack, **Esc** to cancel.

**Cooldowns (default):**

| Type  | Per location | Per player |
| ----- | ------------ | ---------- |
| Bank  | 30 min       | 15 min     |
| ATM   | 10 min       | 7 min      |
| Store | 15 min       | 7 min      |

* Starting a robbery raises a 911 call automatically.
* On-duty players cannot start a robbery (`blockOnDuty = true`).
* The server validates distance, cooldowns, and completion timing, so a modified client cannot skip them.

> **Robberies do not pay out.** No cash or items are ever granted. They are designed as role-play events. If you want rewards, hook your own economy resource into the robbery result.

To add a location, add an entry to `Config.Robbery.locations`:

lua

```lua
{ id = 'store_example', type = 'store', label = '24/7 - Postal 000',
  coords = vector3(0.0, 0.0, 0.0) },
```

`type` must be `bank`, `atm`, or `store`, and `id` must be unique.

***

### Configuration Reference

#### `config.lua` (shared)

| Section                      | What it controls                                               |
| ---------------------------- | -------------------------------------------------------------- |
| `Config.Locale`              | Language (`en` by default). Add languages in `locales.json`    |
| `Config.Notifications`       | Position, duration, max visible, sound                         |
| `Config.Departments`         | Departments, blips, logos, and CAD access flag                 |
| `Config.Emergency`           | Report length, blip duration, priority keywords                |
| `Config.Panic`               | Panic blip duration                                            |
| `Config.AutoDispatch`        | Automatic 911 triggers                                         |
| `Config.Sync`                | Blip and coordinate update intervals (minimum 500ms)           |
| `Config.TabletAnim`          | Tablet animation and prop                                      |
| `Config.Character`           | Character limits, creator location, genders, licenses          |
| `Config.IDCards`             | Card radius, validity, titles, colors                          |
| `Config.Spawn`               | Spawn command, loading time, locations                         |
| `Config.CAD`                 | CAD command, keybind, access, limits, statuses, charges, codes |
| `Config.VehicleRegistration` | Registration limits                                            |
| `Config.Robbery`             | Robbery locations, cooldowns, mini-game difficulty             |

**Notification positions:** `top-right`, `top-left`, `bottom-right`, `bottom-left`.

#### `server_config.lua` (server only)

Holds Discord credentials, role IDs, webhooks, and per-action cooldowns (in seconds):

| Action              | Default |
| ------------------- | ------- |
| `emergencyCall`     | 30      |
| `panic`             | 15      |
| `dutyRequest`       | 5       |
| `supervisorRequest` | 3       |
| `forceOff`          | 2       |
| `calls911Request`   | 2       |
| `dismiss911`        | 2       |
| `clearPanic`        | 3       |
| `cadSearch`         | 1       |
| `cadWrite`          | 1       |
| `cadFlagWrite`      | 1       |
| `vehicleRegister`   | 5       |
| `vehicleList`       | 2       |
| `handCard`          | 3       |

#### Adding a department

A department needs entries in **both** config files, or the resource will fail its startup check.

1. In `config.lua`, add it to `Config.Departments` (label, blip, `cad`, logo). If it should use the CAD, also add its key to `Config.CAD.accessDepartments`.
2. In `server_config.lua`, add it to `ServerConfig.Departments` with `dutyRole`, `supervisorRole`, and `webhookThumbnail`, and add its webhook under `ServerConfig.Webhooks`.
3. Put its logo in `html/images/`.

Setting `cad = false` on a department stops its members from opening the CAD without affecting duty.

***

### Integrations

#### Raising a dispatch alert from another resource

Other resources, such as alarms, custom robbery scripts, or crash detection, can push alerts into the same dispatch queue. The alert appears to every on-duty CAD officer exactly like a player 911 call, with no caller identity attached.

lua

```lua
exports['X1S-LifeSystem']:CreateDispatchAlert({
    title    = 'Alarm Triggered',
    coords   = vector3(0.0, 0.0, 0.0),
    street   = 'Optional street label',
    priority = 'high' -- optional: 'high', 'medium', or 'low'
})
```

| Field      | Required | Notes                                                                           |
| ---------- | -------- | ------------------------------------------------------------------------------- |
| `title`    | No       | Shown as the call reason (up to 96 characters)                                  |
| `coords`   | **Yes**  | `vector3` or a table with `x`, `y`, `z`                                         |
| `street`   | No       | Location label                                                                  |
| `priority` | No       | If omitted or invalid, it is classified from `title` using the 911 keyword list |

The export returns `true` and the alert ID on success, or `false` and an error message.

***

### Troubleshooting

**Nobody can go on duty.** Check the console at startup for the message that Discord credentials are not configured. Confirm the bot token and guild ID are set, the bot is in your Discord server, the player has Discord linked to FiveM, and the player holds the department's duty role.

**"oxmysql is not running" or database connection errors in the console.** Make sure `ensure oxmysql` comes before `ensure X1S-LifeSystem` and your oxmysql connection string is correct.

**The resource fails on start with a "Missing server configuration" error.** A department exists in `Config.Departments` but not in `ServerConfig.Departments`. See Adding a department.

**The menu shows but the mouse does not work.** Another resource may be taking NUI focus at the same time. Try `/switchcharacter` to reopen the flow, and if it keeps happening, open a support ticket with your resource list.

**Menu music does not play.** The game may be blocking autoplay. Click anywhere on the screen and it will start. Also check that the player's music is not muted or set to zero in the on-screen control.

**Cannot open the CAD.** The player must be on duty, in a department with `cad = true`, and that department must be in `Config.CAD.accessDepartments`.

**The 911 queue is empty after a restart.** This is expected. Active calls are stored in memory and are cleared when the resource restarts.

**Robberies give no money.** This is by design. See Robberies.

**I want to change the 10-codes or penal codes.** Use the CAD Admin tab. Editing the lists in `config.lua` only affects a fresh database, because they are seeded once.

***

### Updates

The resource checks for a newer version on start and prints the result in the server console.

***

### Support

**SUPPORT — YES | DISCORD TICKETS ONLY**

For support, please open a ticket in the X1Studios Discord.

[Open X1Studios Discord](https://discord.gg/TqcPD9Xee3)
