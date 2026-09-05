# Installation

## X1Studios Simple Duty System

> **Deprecated Resource**
>
> This resource is no longer actively maintained or updated. Installation instructions are provided for existing users who wish to continue using the resource.

### Requirements

Before installing the Simple Duty System, make sure the following resources are installed and running on your server.

#### OX\_Lib

Required for the duty menu.

```
ox_lib
```

#### Chat

Required for the system's chat notifications.

```
chat
```

Make sure both resources are started before the X1Studios Duty System.

***

## 1. Download the Resource

Download the **X1Studios Simple Duty System** resource and extract it into your server's resources directory.

For example:

```
resources/
└── [x1studios]/
    └── X1S-SimpleDutySystem/
```

The resource folder name can be different depending on the version you received.

***

## 2. Install OX\_Lib

Make sure OX\_Lib is installed correctly on your server.

Your resource structure should contain:

```
resources/
└── ox_lib/
```

OX\_Lib must be started before the Simple Duty System.

***

## 3. Verify Chat

The FiveM Chat resource is required for the duty notifications.

Make sure your server has:

```
chat
```

installed and running.

***

## 4. Configure the Script

Open the resource's configuration file and review the available settings.

Configure the options provided by your version of the resource, including:

* Departments
* Department names
* Callsigns
* Duty blips
* Permissions
* Discord logging
* Discord webhook
* Other available settings

Do not remove configuration options unless you understand what they control.

> **Note:** Configuration options can vary between versions of the resource. Use the configuration file included with your copy of the script as the authoritative reference.

***

## 5. Configure Departments

Add or modify the departments available through the duty menu.

You can configure multiple departments and create additional department entries as needed.

For each department, review the available settings for:

* Department name
* Callsigns
* Permissions
* Blips
* Duty behavior

***

## 6. Configure Discord Permissions

If your version of the resource uses Discord ACE permissions, configure the appropriate Discord roles and ACE permissions according to the included configuration.

This allows you to restrict the duty system to authorized department members.

Make sure the Discord permission system you use is already installed and functioning correctly before testing the duty resource.

***

## 7. Configure Discord Logging

If you want duty activity sent to Discord, configure the provided Discord webhook option.

The webhook can be used to log duty activity such as:

* Going on duty
* Going off duty
* Department activity

Keep your webhook private and do not publicly share it.

***

## 8. Add the Resource to server.cfg

Add the required resources in the appropriate startup order.

For example:

```cfg
ensure ox_lib
ensure chat
ensure X1S-SimpleDutySystem
```

Use the actual resource folder name if yours is different.

OX\_Lib should be started before the duty system.

***

## 9. Restart the Server

After configuring the resource, restart your FiveM server.

Check the server console for any errors related to:

```
ox_lib
chat
X1S-SimpleDutySystem
```

If no errors are displayed, continue to testing.

***

## 10. Test the Duty Menu

Join the server with an account that has the appropriate permissions.

Use:

```
/dutymenu
```

The OX\_Lib duty menu should open.

Test the available department and duty options.

***

## 11. Test Duty Status

After selecting a department or duty option, verify that:

* Your duty status changes correctly.
* Chat notifications appear.
* Your configured callsign is applied.
* Your department is displayed correctly.
* Duty blips function correctly.
* Discord logging works if enabled.

Repeat the test when going off duty.

***

## Troubleshooting

### `/dutymenu` Does Nothing

Check that:

* The resource is running.
* You have the required permissions.
* OX\_Lib is running.
* The command has not been overridden by another resource.

Check the server console for errors.

### OX\_Lib Menu Does Not Open

Verify that:

```cfg
ensure ox_lib
```

starts before the duty resource.

Also verify that you are using a compatible version of OX\_Lib.

### Notifications Are Not Appearing

Verify that the FiveM Chat resource is installed and running:

```cfg
ensure chat
```

Check the console for Chat-related errors.

### Discord Permissions Are Not Working

Check:

* Discord role configuration.
* ACE permission configuration.
* Discord permission resource configuration.
* The player's Discord account and roles.
* Any relevant server console errors.

### Discord Logs Are Not Sending

Verify that:

* The webhook URL is correct.
* The webhook still exists.
* The webhook has not been deleted or regenerated.
* The resource is configured to use Discord logging.
* There are no webhook-related errors in the server console.

### Duty Blips Are Not Working

Check the department and blip configuration included with the resource.

Also verify that the player successfully entered duty and that no configuration option is disabling the blip.

***

## Updating

This resource is **deprecated and no longer receives updates**.

There are currently no active update instructions for this resource.

If you experience compatibility issues with newer FiveM artifacts or other resources, consider transitioning to a newer X1Studios duty system if one is available.

### Support

For community support, questions, and information about newer X1Studios resources, join the official Discord:

[**https://discord.gg/TqcPD9Xee3**](https://discord.gg/TqcPD9Xee3)

X1Studios also provides previews and releases for:

* FiveM Scripts
* EUP Packs
* Custom Liveries
* YMAPs
* Other FiveM Development Projects
