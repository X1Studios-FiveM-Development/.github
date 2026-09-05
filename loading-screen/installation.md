# Installation

## X1Studios Loading Screen

### Installation Guide

Get the X1Studios Loading Screen installed and configured on your FiveM server with the steps below.

***

### Requirements

**Required Dependencies:** None

The X1Studios Advanced FiveM Loading Screen is **fully standalone** and does not require:

* QBCore
* QBox
* ESX
* vMenu
* ox\_lib
* Any additional scripts or frameworks

It can be installed on virtually any FiveM server.

***

## 1. Download the Resource

Download the latest version of the **X1Studios Advanced FiveM Loading Screen**.

After downloading, extract the resource using a program such as:

* WinRAR
* 7-Zip

You should have a resource folder containing the loading screen files.

***

## 2. Locate Your FiveM Server

Navigate to your FiveM server's resources directory.

A typical structure will look similar to:

```
server-data/
└── resources/
    ├── [local]/
    ├── [standalone]/
    └── X1S-LoadingScreen/
```

You may place the loading screen inside an existing resource category or create your own folder.

For example:

```
resources/
└── [X1Studios]/
    └── X1S-LoadingScreen/
```

> The exact resource folder name may vary depending on the version you downloaded.

***

## 3. Verify the Resource Files

Make sure the loading screen files are directly inside the resource folder.

For example:

```
X1S-LoadingScreen/
├── config.js
├── fxmanifest.lua
├── index.html
├── css/
├── js/
├── images/
└── ...
```

Do **not** place the resource inside another folder by accident.

Incorrect:

```
resources/
└── X1S-LoadingScreen/
    └── X1S-LoadingScreen/
        ├── fxmanifest.lua
        └── index.html
```

Correct:

```
resources/
└── X1S-LoadingScreen/
    ├── fxmanifest.lua
    └── index.html
```

***

## 4. Configure the Loading Screen

Open:

```
config.js
```

This is where you can customize the loading screen.

Depending on the version, configuration options can include:

* Staff members
* Staff names
* Staff information
* Discord link
* YouTube link
* Website link
* Background images
* Background slideshow
* Music
* Other loading screen information

Open the configuration file with a code editor such as **Visual Studio Code**.

> Do not remove required configuration fields unless you know they are optional. Keep the existing structure of the configuration file intact.

***

## 5. Add Your Backgrounds

The loading screen supports a dynamic background slideshow.

Locate the background/image directory included with the resource and add your desired images.

Recommended:

```
.jpg
.jpeg
.png
.webp
```

Use appropriately sized images to maintain good visual quality.

After adding your images, make sure they are referenced correctly by the configuration if the resource version requires manual configuration.

***

## 6. Configure Staff Members

The loading screen allows you to customize the staff information displayed on the interface.

Open:

```
config.js
```

Locate the staff configuration section and replace the example information with your own staff members.

For example:

```
Owner
Developer
Management
Moderator
Support
```

Use the configuration structure already provided with your version of the resource.

***

## 7. Configure Social Media

You can configure the social media buttons displayed at the bottom of the loading screen.

Common links include:

```
Discord
YouTube
Website
```

Replace the default/example URLs with your server or community links.

When a player clicks a supported social icon, the configured link can be opened in their browser.

***

## 8. Configure Music

The loading screen includes a built-in music player with controls for:

* Play
* Pause
* Volume

If your version includes configurable music tracks, add or replace the provided audio according to the configuration included with the resource.

Make sure any audio files are included in the resource and properly referenced.

***

## 9. Add the Resource to server.cfg

Open your server's:

```
server.cfg
```

Add the loading screen resource to your startup configuration:

```cfg
ensure X1S-LoadingScreen
```

Replace `X1S-LoadingScreen` with the exact name of your resource folder if it differs.

For example, if your folder is:

```
X1Studios-LoadingScreen
```

Use:

```cfg
ensure X1Studios-LoadingScreen
```

***

## 10. Restart Your Server

After configuring the resource, restart your FiveM server.

A full server restart is recommended when initially installing the loading screen.

Once the server has started, connect to the server from FiveM.

***

## 11. Test the Loading Screen

Connect to your server and verify that the loading screen appears correctly.

Check the following:

#### Loading Interface

* Loading screen displays correctly
* UI is positioned correctly
* Animations work
* Loading bar appears

#### Backgrounds

* Background images load
* Slideshow works
* Images transition correctly

#### Staff

* Staff information displays correctly
* Names are correct
* No broken images or text appear

#### Social Links

* Discord button works
* YouTube button works
* Website button works

#### Music

* Music player appears
* Play button works
* Pause button works
* Volume controls work

***

## Troubleshooting

### Loading Screen Does Not Appear

Verify that the resource is started in `server.cfg`:

```cfg
ensure X1S-LoadingScreen
```

Also verify that the resource folder contains:

```
fxmanifest.lua
```

and that the resource is not nested inside another folder.

***

### Resource Failed to Start

Check the server console for errors.

Common causes include:

* Incorrect folder structure
* Missing resource files
* Incorrect configuration
* Invalid configuration syntax
* Incorrect resource name in `server.cfg`

***

### Backgrounds Are Not Showing

Check that:

* The image files are inside the correct directory
* The filenames are correct
* The file extensions are supported
* The images are correctly referenced in `config.js`, if required

Be careful with capitalization and spelling.

***

### Social Links Do Not Work

Open:

```
config.js
```

and verify that your URLs are correct.

For example:

```
https://discord.gg/yourserver
```

Make sure there are no missing characters or quotation marks.

***

### Music Is Not Playing

Check that:

* The audio files are present
* The configured file/path is correct
* The browser console does not report an audio error
* The music configuration matches the version of the resource you're using

Some browsers and FiveM NUI environments may also restrict certain external audio sources.

***

## Updating the Loading Screen

When a new version is released:

1. Stop your FiveM server.
2. Back up your current loading screen.
3. Download the newest version.
4. Remove the old resource files.
5. Install the new resource.
6. Reapply your configuration if necessary.
7. Verify your `config.js`.
8. Confirm `server.cfg` is still using the correct resource name.
9. Restart the server.
10. Test the loading screen.

> Always keep a backup of your customized `config.js` before updating.

***

## Installation Complete

Your **X1Studios Advanced FiveM Loading Screen** should now be installed and ready for use.

For support, configuration assistance, or bug reports, open a support ticket in the **X1Studios Discord**:

[https://discord.gg/TqcPD9Xee3](https://discord.gg/TqcPD9Xee3)

**X1Studios - FiveM Development**
