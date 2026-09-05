# Documentaion

## X1Studios **Whos Talking?**

### Overview

The **X1Studios Whos Talking?** is a lightweight voice identification system for FiveM servers using **PMA-Voice**.

Inspired by the voice display system used by **OCRP**, the script provides players with a simple on-screen list showing who is currently talking.

The system is designed to make voice communication easier to identify during roleplay by displaying the player's **server ID and name** whenever they are actively speaking.

***

## Features

### Active Speaker Display

The script automatically detects players who are currently speaking through PMA-Voice and displays their information on screen.

The display follows a simple layout:

```
------------
Talking:
[ID] NAME
[ID] NAME
------------
```

The **"Talking:"** label is displayed in red, while the speaker's ID and name are displayed in white.

***

## Multiple Speakers

The system supports displaying multiple players who are talking at the same time.

For example:

```
------------
Talking:
[12] John Doe
[27] Havoc Sheriff
[45] Princess Ling-Sheriff
------------
```

Players are automatically added to and removed from the list based on their current voice activity.

***

## Player Information

Each active speaker is identified using:

* Server ID
* Player name

This allows players to quickly determine exactly who is speaking without needing to rely solely on voice recognition.

***

## PMA-Voice Integration

The Talking Indicator is specifically designed to work with **PMA-Voice**.

The script monitors PMA-Voice voice activity and uses that information to determine which players should appear in the talking list.

***

## Universal Server Compatibility

The script is designed to work with any FiveM server that uses PMA-Voice.

It does not require:

* QBCore
* QBox
* ESX
* vMenu
* Any other framework

As long as the server uses PMA-Voice, the Talking Indicator can be used.

***

## Lightweight Design

The script is designed to perform its voice activity checks efficiently while keeping the UI simple.

The display only shows relevant information when players are actively speaking, keeping the interface clean and unobtrusive during gameplay.

***

## UI Layout

The default display follows the OCRP-inspired layout:

```
------------
Talking:
[ID] NAME
[ID] NAME
------------
```

#### Talking Header

The `Talking:` header is displayed in **red**.

#### Player Information

The player's:

```
[ID] NAME
```

is displayed in **white**.

***

## Requirements

#### Required

**PMA-Voice**

The server must already have PMA-Voice installed and functioning.

No other framework or dependency is required.

***

## Compatibility

X1Studios Whos Talking? is compatible with FiveM servers using:

* PMA-Voice
* QBCore + PMA-Voice
* QBox + PMA-Voice
* ESX + PMA-Voice
* vMenu + PMA-Voice
* Standalone + PMA-Voice
* Custom frameworks + PMA-Voice

The script does not depend on the framework itself.

***

## How It Works

The system operates automatically:

**1.** A player begins speaking through PMA-Voice.

**2.** The Talking Indicator detects the active speaker.

**3.** The player's server ID and name are added to the UI.

**4.** Other players can see who is currently speaking.

**5.** When the player stops speaking, they are removed from the list.

If multiple players are speaking simultaneously, each active speaker can be displayed.

***

## Support

For support with the X1Studios Whos Talking?, open a support ticket in the official X1Studios Discord.

**Support is provided through Discord tickets only.**

#### X1Studios Discord

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

***

## Community

Join the X1Studios Discord for:

* Upcoming FiveM scripts
* Free FiveM EUP packs
* Custom liveries
* Development previews
* New releases
* Updates
* Support

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
