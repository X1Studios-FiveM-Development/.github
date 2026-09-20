# Installation

This guide walks you through installing X1S Life System from a fresh download to a working first join. Most servers can finish in 15 to 20 minutes. The Discord setup takes the longest.

***

### Before You Begin

Make sure you have the following ready:

| Item                                                                                          | Why you need it                                                            |
| --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| A running FiveM server with access to `server.cfg`                                            | To start the resource                                                      |
| A MySQL or MariaDB database                                                                   | To store characters, vehicles, warrants, arrests, citations, and incidents |
| [`oxmysql`](https://github.com/overextended/oxmysql) installed and connected to that database | The only dependency, used as a database driver                             |
| A Discord server you manage                                                                   | For duty role verification and logs                                        |
| A FiveM artifact with Lua 5.4 support                                                         | The resource uses `lua54 'yes'`                                            |

If you previously ran **X1S-AdvDutySystem** or **X1S-SpawnSelector**, remove or stop them before installing. X1S Life System replaces both, and running them together will cause conflicts.

***

### Step 1: Install oxmysql

Skip this step if `oxmysql` is already installed and working.

1. Download `oxmysql` and place it in your `resources` folder.
2. Add your database connection string to `server.cfg`:

cfg

```cfg
set mysql_connection_string "mysql://USERNAME:PASSWORD@HOST/DATABASE_NAME"
```

3. Make sure `ensure oxmysql` is in `server.cfg`.

***

### Step 2: Add the Resource

1. Extract the download.
2. Copy the `X1S-LifeSystem` folder into your server's `resources` directory.

> **Keep the folder name exactly `X1S-LifeSystem`.** If your download extracted as something like `X1S-LifeSystem-main` or `X1S-LifeSystem (1)`, rename it. Other resources call the script by this name.

Your folder should look like this:

```
resources/
└── X1S-LifeSystem/
    ├── fxmanifest.lua
    ├── config.lua
    ├── server_config.lua
    ├── locales.json
    ├── client/
    ├── server/
    ├── html/
    └── sql/
```

If `fxmanifest.lua` is not directly inside the `X1S-LifeSystem` folder (for example, it is inside a second folder of the same name), move the inner folder up one level.

***

### Step 3: Import the Database

1. Open your database tool (HeidiSQL, phpMyAdmin, DBeaver, or the MySQL command line).
2. Select the database your oxmysql connection string points to.
3. Import `X1S-LifeSystem/sql/database.sql`.

Command line example:

bash

```bash
mysql -u USERNAME -p DATABASE_NAME < sql/database.sql
```

This creates the tables the script needs:

`x1s_characters`, `x1s_vehicles`, `x1s_vehicle_history`, `x1s_vehicle_bolos`, `x1s_warrants`, `x1s_arrests`, `x1s_citations`, `x1s_incidents`, `x1s_ten_codes`, and `x1s_penal_codes`.

The file uses `CREATE TABLE IF NOT EXISTS`, so importing it again will not overwrite existing tables.

> **Upgrading an existing install?** Also run the migration statements at the bottom of `sql/database.sql` once. They add the `brand` column to vehicles and the `address` column to characters. Fresh installs already include both.

***

### Step 4: Set Up Discord

Duty verification, supervisor permissions, and CAD admin permissions are all controlled by Discord roles. You need a bot, role IDs, and (optionally) webhooks.

#### 4.1 Turn on Developer Mode

In Discord, open **User Settings → Advanced** and turn on **Developer Mode**. This lets you right-click servers, roles, and channels to copy their IDs.

#### 4.2 Create the bot

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications) and click **New Application**.
2. Open the **Bot** tab and click **Reset Token**. Copy the token and store it somewhere safe. You will only see it once.
3. On the same tab, enable **Server Members Intent**.
4. Open **OAuth2 → URL Generator**, tick the `bot` scope, and open the generated link to add the bot to your Discord server.

#### 4.3 Collect your IDs

Right-click each item and choose **Copy ID**:

| What                               | Where to right-click                    |
| ---------------------------------- | --------------------------------------- |
| Guild (server) ID                  | Your server icon                        |
| LEO role ID                        | The role pinged on 911 calls            |
| Admin role ID                      | The role that can use the CAD Admin tab |
| Duty role ID, per department       | Each department's on-duty role          |
| Supervisor role ID, per department | Each department's supervisor role       |

For roles, open **Server Settings → Roles**, right-click the role, and choose **Copy Role ID**.

#### 4.4 Create webhooks (optional but recommended)

For each log channel, open **Channel Settings → Integrations → Webhooks → New Webhook** and copy the URL. You can point every log at one channel or split them across several. See the full webhook list below.

#### 4.5 Add the values to `server.cfg`

Adding your values as convars keeps them out of the resource folder. Use `set`, **not** `setr`, because `setr` sends the value to players.

cfg

```cfg
set x1s_bot_token "YOUR_BOT_TOKEN"
set x1s_guild_id "YOUR_GUILD_ID"
set x1s_leo_role_id "YOUR_LEO_ROLE_ID"
set x1s_admin_role_id "YOUR_ADMIN_ROLE_ID"

set x1s_lspd_duty_role "ROLE_ID"
set x1s_lspd_supervisor_role "ROLE_ID"
set x1s_bcso_duty_role "ROLE_ID"
set x1s_bcso_supervisor_role "ROLE_ID"
set x1s_sast_duty_role "ROLE_ID"
set x1s_sast_supervisor_role "ROLE_ID"
set x1s_sagw_duty_role "ROLE_ID"
set x1s_sagw_supervisor_role "ROLE_ID"

set x1s_lspd_webhook "WEBHOOK_URL"
set x1s_bcso_webhook "WEBHOOK_URL"
set x1s_sast_webhook "WEBHOOK_URL"
set x1s_sagw_webhook "WEBHOOK_URL"
set x1s_dispatch_webhook "WEBHOOK_URL"
set x1s_panic_webhook "WEBHOOK_URL"
```

Alternatively, you can type your values straight into `server_config.lua`. Each setting is written as `GetConvar('name', 'fallback')`, so if no convar is set, the value typed in the file is used.

> **Keep your credentials private.** Never post your bot token or webhook URLs publicly, and never commit `server_config.lua` with real values in it. If any of them are ever exposed, regenerate them in Discord.

#### Webhook and log convars

Each log event has its own webhook, in the form `x1s_log_<name>_webhook`. Any left empty or containing `_HERE` are skipped, so you can turn logging on one event at a time.

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

#### What happens if Discord is not configured

If the bot token or guild ID is empty (or contains `_HERE`), the server console prints a warning and **all duty role checks are denied**. Nobody will be able to go on duty until this step is done.

***

### Step 5: Add the Resource to `server.cfg`

Add both lines, with `oxmysql` **first**:

cfg

```cfg
ensure oxmysql
ensure X1S-LifeSystem
```

If you use convars from Step 4, place those `set` lines **above** the `ensure` lines so they are loaded before the resource starts.

***

### Step 6: Start the Server and Check the Console

Restart your server and look for these messages:

| Console message                                                 | Meaning                                        |
| --------------------------------------------------------------- | ---------------------------------------------- |
| `[X1S] Database connection OK.`                                 | oxmysql is connected and working               |
| The **X1 Studios** banner                                       | The resource started                           |
| `[X1S][CAD] Seeded ... ten-codes ...` and `... penal codes ...` | First-run setup filled the CAD reference lists |
| `[Update Checker] ... is up to date!`                           | Your version is current                        |

Problems you may see:

| Console message                              | Fix                                                                                        |
| -------------------------------------------- | ------------------------------------------------------------------------------------------ |
| `oxmysql is not running`                     | Add `ensure oxmysql` above `ensure X1S-LifeSystem`                                         |
| `Could not reach the database via oxmysql`   | Check your `mysql_connection_string`                                                       |
| `Discord bot credentials are not configured` | Finish Step 4                                                                              |
| `Missing server configuration for ...`       | A department exists in `config.lua` but not in `server_config.lua` (see the documentation) |

***

### Step 7: Test It

Join your server and run through this checklist:

* [ ] The **character creator** appears on first join with the menu music playing
* [ ] You can create a character and it appears in the **character selector**
* [ ] Selecting the character opens the **spawn selector**
* [ ] Picking a location spawns you in the world
* [ ] `/dutymenu` lets you go on duty (requires the department's Discord duty role)
* [ ] `/cad` or **F6** opens the CAD while on duty
* [ ] `/911` files a call and on-duty officers receive it
* [ ] `/registervehicle` registers a vehicle and it appears in the CAD vehicle search
* [ ] `/handid` shows your ID card

If every item works, you are done.

***

### Good to Know

* **Appearance is not included.** The creator handles identity only (name, date of birth, gender, and height). Use your own clothing or appearance resource for looks.
* **Active 911 calls are kept in memory.** The call queue clears when the resource restarts.
* **Robberies do not pay out.** They are role-play events. No cash or items are given.
* **10-codes and penal codes are seeded once.** After the first start, edit them in-game from the CAD **Admin** tab. Editing `config.lua` afterward only affects a fresh database.

***

### Updating

1. Back up your current `X1S-LifeSystem` folder and your database.
2. Replace the resource files with the new version. Keep your own `config.lua` and `server_config.lua` (or re-apply your changes to the new copies).
3. Run any new migration statements from the bottom of `sql/database.sql`.
4. Restart the resource.

***

### Next Steps

* Read the full **X1S Life System Documentation** for commands, keybinds, configuration options, and feature guides.
* Customize departments, spawn locations, robbery locations, and CAD charges in `config.lua`.

***

### Support

**SUPPORT — YES | DISCORD TICKETS ONLY**

For support, please open a ticket in the X1Studios Discord.

[Open X1Studios Discord](https://discord.gg/TqcPD9Xee3)

