# Installation

## X1Studios Whos Talking?

### Requirements

The only required dependency is:

#### PMA-Voice

PMA-Voice must already be installed and functioning on your FiveM server.

No framework is required.

The script works with:

* Standalone
* QBCore
* QBox
* ESX
* vMenu
* Custom frameworks

***

## Step 1 — Install PMA-Voice

If PMA-Voice is not already installed on your server, install it first.

The Talking Indicator relies on PMA-Voice to determine when players are speaking.

Make sure PMA-Voice is working correctly before continuing.

***

## Step 2 — Download The Script

Download the latest version of the **X1Studios Whos Talking?**.

Extract the resource using:

* 7-Zip
* WinRAR
* Windows File Explorer

Keep the resource's original folder structure intact.

***

## Step 3 — Add The Resource To Your Server

Place the Talking Indicator resource inside your server's resources directory.

For example:

```
resources/
├── [voice]/
│   └── pma-voice/
│
└── X1S-Talking/
```

The exact folder name may differ depending on the version of the resource.

***

## Step 4 — Verify PMA-Voice

Before starting the Talking Indicator, verify that PMA-Voice is running.

Your server configuration should start PMA-Voice before the Talking Indicator.

For example:

```cfg
ensure pma-voice
ensure X1S-Talking
```

If your PMA-Voice resource is located inside a category folder, use the appropriate resource name for your server.

***

## Step 5 — Add The Resource To server.cfg

Open your:

```
server.cfg
```

Add:

```cfg
ensure X1S-Talking
```

Make sure the resource name matches the actual folder name.

***

## Step 6 — Restart The Server

Restart your FiveM server after adding the resource.

You can also start the resource manually from the server console:

```
ensure X1S-Talking
```

Check the server console for any errors.

***

## Step 7 — Test The Talking Indicator

Connect to your server with at least one other player.

Have the player speak using PMA-Voice.

The Talking Indicator should display something similar to:

```
------------
Talking:
[12] John Doe
------------
```

When multiple players are talking:

```
------------
Talking:
[12] John Doe
[27] Havoc Sheriff
------------
```

When the player stops speaking, their name should disappear from the list.

***

## Step 8 — Verify Player Information

Confirm that the display correctly shows:

* Player server ID
* Player name
* Talking status

The information should update automatically as players begin and stop speaking.

***

## Troubleshooting

### Talking Indicator Does Not Appear

If the UI does not appear:

* Verify the resource is running.
* Verify PMA-Voice is running.
* Check the server console for errors.
* Check the client console for errors.
* Verify the resource name in `server.cfg`.
* Restart the resource.

***

### Players Are Not Appearing When Speaking

If players can speak but are not appearing in the Talking list:

* Verify PMA-Voice is functioning correctly.
* Confirm the player is actually transmitting through PMA-Voice.
* Verify PMA-Voice starts before the Talking Indicator.
* Restart both resources.
* Check for client-side errors.

***

### Names Are Not Displaying Correctly

If the server ID appears but the player name does not:

* Check the client console for errors.
* Verify the resource is running the correct version.
* Restart the resource.
* Have the affected player reconnect to the server.

***

### PMA-Voice Works But The Indicator Does Not

If voice communication works normally but the Talking Indicator does not respond:

1. Verify PMA-Voice starts before the Talking Indicator.
2. Restart the Talking Indicator.
3. Restart the FiveM client.
4. Check both client and server consoles for errors.
5. Verify that you are running the latest version of both resources.

***

## Resource Order

PMA-Voice should start before the Talking Indicator.

Recommended order:

```cfg
ensure pma-voice
ensure X1S-Talking
```

The Talking Indicator relies on PMA-Voice being available.

***

## Updating The Script

When installing a new version:

1. Stop the Talking Indicator resource.
2. Back up your existing files if you have made configuration changes.
3. Download the latest version.
4. Replace the old resource files.
5. Start the resource again.
6. Test voice communication.
7. Test the Talking Indicator with multiple players.

***

## Installation Complete

The **X1Studios Whos Talking?** is now installed.

Once players begin speaking through PMA-Voice, their server ID and name will automatically appear in the talking list.

The default layout is:

```
------------
Talking:
[ID] NAME
[ID] NAME
------------
```

For support, open a ticket in the official X1Studios Discord.

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
