# Installation

## X1Studios CarPlay

### Requirements

Before installing X1Studios CarPlay, make sure your server has the required dependency installed.

#### Required Dependency

**xsound**

GitHub:\
[https://github.com/Xogy/xsound](https://github.com/Xogy/xsound)

X1Studios CarPlay uses xsound for audio playback and vehicle-based 3D audio.

***

## Step 1 — Download CarPlay

Download the latest version of **X1Studios CarPlay**.

Extract the downloaded resource using a program such as:

* 7-Zip
* WinRAR
* Windows File Explorer

You should have a resource folder containing the CarPlay files.

***

## Step 2 — Install xsound

Download xsound from the official GitHub repository:

[https://github.com/Xogy/xsound](https://github.com/Xogy/xsound)

Place the xsound resource inside your server's resources directory.

For example:

```
resources/
├── [standalone]/
│
├── xsound/
│
└── X1S-CarPlay/
```

The exact folder structure may be different depending on how your server organizes resources.

***

## Step 3 — Install X1S-CarPlay

Place the **X1S-CarPlay** resource inside your server's resources directory.

Example:

```
resources/
├── xsound/
└── X1S-CarPlay/
```

Do not rename individual files inside the resource unless instructed by X1Studios.

***

## Step 4 — Configure the Script

Open the CarPlay configuration file included with the resource.

Configure the available options according to your server.

Depending on the version of X1S-CarPlay, configuration options may include:

* Framework
* CarPlay keybind
* Usable item
* Item requirement
* Blacklisted songs
* Audio settings
* Other server-specific options

Make sure your framework configuration matches your server.

For example:

```
Standalone
QBCore
QBox
ESX
```

***

## Step 5 — Configure the CarPlay Item

If you want players to require an item before using CarPlay, enable the item requirement in the configuration.

You will then need to make sure the configured item exists in your framework's item system.

For example:

```
carplay
```

The exact item name should match the item configured inside X1S-CarPlay.

If you are running the script in **Standalone mode**, follow the configuration provided with the resource for the standalone item behavior.

***

## Step 6 — Add the Resource to server.cfg

Open your server's:

```
server.cfg
```

Make sure xsound starts before X1S-CarPlay.

Example:

```cfg
ensure xsound
ensure X1S-CarPlay
```

The resource names must match the actual folder names inside your resources directory.

***

## Step 7 — Restart Your Server

Restart the FiveM server after adding the resources and configuration.

Alternatively, you can start the resources from the server console:

```
ensure xsound
ensure X1S-CarPlay
```

Check the server console for any errors.

***

## Step 8 — Test CarPlay

Once the server has started, join the server and test the system.

Use:

```
/carplay
```

This should open the CarPlay interface.

You can also use the configured CarPlay keybind.

***

## Step 9 — Test Music Playback

Once CarPlay is open:

1. Enter a valid YouTube URL.
2. Start playback.
3. Enter a vehicle.
4. Verify that the music can be heard.
5. Test the volume controls.
6. Test pause and resume.
7. Test the playback progress bar.
8. Add another song to the queue.
9. Test saved music.
10. Test playlist functionality.

Also test the audio from outside the vehicle to verify that the 3D and muffled exterior audio are functioning correctly.

***

## Troubleshooting

### CarPlay Does Not Open

If `/carplay` does not open:

* Make sure X1S-CarPlay is started.
* Check the server console for errors.
* Verify that the resource name in `server.cfg` is correct.
* Try restarting the resource.
* Verify that the NUI files are present.

***

### Music Does Not Play

If CarPlay opens but music does not play:

* Verify that xsound is installed.
* Verify that xsound starts before X1S-CarPlay.
* Check the server console for errors.
* Make sure you are using a valid YouTube URL.
* Restart both resources.

Your `server.cfg` should contain:

```cfg
ensure xsound
ensure X1S-CarPlay
```

***

### CarPlay Item Does Not Work

If the item requirement is enabled but the item does not work:

* Verify that the item exists in your framework and inventory.
* Verify that the item name matches the configuration.
* Verify that the correct framework is selected.
* Restart the server after changing item configuration.

***

### Framework Errors

If you receive framework-related errors:

1. Verify the selected framework in the configuration.
2. Make sure the required framework is running.
3. Verify that the framework starts before X1S-CarPlay.
4. Check the server console for additional errors.

***

## Recommended Resource Order

For framework-based servers, make sure your dependencies are started before CarPlay.

A general example:

```cfg
ensure qb-core -- CHANGE DEPENDING ON YOUR FRAMEWORK
ensure xsound
ensure X1S-CarPlay
```

Your actual startup order may differ depending on your server's framework and other resources.

***

## Updating X1S-CarPlay

Before updating the resource:

1. Stop the existing X1S-CarPlay resource.
2. Create a backup of your current configuration.
3. Replace the old resource files with the new version.
4. Reapply any custom configuration if necessary.
5. Verify that xsound is still installed.
6. Start the updated resource.
7. Test CarPlay functionality.

Always check the release information for the version you are installing before replacing files.

***

## Installation Complete

X1Studios CarPlay should now be installed and ready for use.

Players can open CarPlay with:

```
/carplay
```

or through the configured keybind.

For additional assistance, open a support ticket in the official X1Studios Discord.

**X1Studios Discord**

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)
