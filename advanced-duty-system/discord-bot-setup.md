# Discord Bot Setup

## Discord Bot Setup

The X1Studios Duty Systems use a Discord bot to verify Discord roles and control who is allowed to access certain duty system features.

Before configuring the script, you will need to create a Discord application, create a bot, invite it to your Discord server, and configure the required Discord role IDs.

### Requirements

You will need:

* A Discord server
* Discord Developer Portal access
* A Discord Bot
* Your Discord **Guild ID**
* Your Discord **Bot Token**
* The Discord **Role IDs** you want to use for permissions

***

### 1. Create Your Discord Application

Go to the [Discord Developer Portal](https://discord.com/developers/applications).

1. Log into your Discord account.
2. Click **New Application**.
3. Give your application a name.
4. Click **Create**.

You can name the application whatever you want. For example:

`X1Studios Duty Bot`

***

### 2. Create the Bot

Once your application has been created:

1. Open your application.
2. Select **Bot** from the left-side menu.
3. Click **Add Bot**.
4. Confirm that you want to create the bot.

Your application now has a Discord bot.

#### Important: Bot Token

Under the **Bot** section, you will find your bot's token.

Your bot token is a **private credential** and should NEVER be shared publicly.

Do not post your token in:

* Discord
* GitHub
* Documentation
* Screenshots
* Public configuration files
* Support tickets

If your token is accidentally exposed, immediately regenerate it from the Discord Developer Portal.

Your configuration should look similar to:

```lua
BotToken = "YOUR_BOT_TOKEN_HERE"
```

**Never use the example value above as your actual token.**

***

## 3. Enable Required Intents

Depending on the version of the duty system, the bot may need Discord Gateway intents to check server members and their roles.

In the Discord Developer Portal:

1. Open your application.
2. Go to **Bot**.
3. Find **Privileged Gateway Intents**.
4. Enable:

**Server Members Intent**

5. Save your changes.

If your specific version of the script requires additional intents, enable those as indicated in the script's configuration.

***

## 4. Invite the Bot to Your Server

Go to:

**OAuth2 → URL Generator**

Select:

#### Scopes

* `bot`

#### Bot Permissions

Give the bot the permissions required by your configuration.

For role/member verification, the bot generally needs permission to view the server and access member information.

Generate the URL and open it in your browser.

Select your Discord server and authorize the bot.

After authorization, the bot should appear in your server's member list.

***

## 5. Find Your Guild ID

Your **Guild ID** is your Discord server's unique ID.

#### Enable Developer Mode

In Discord:

1. Open **User Settings**.
2. Go to **Advanced**.
3. Enable **Developer Mode**.

#### Copy Your Guild ID

1. Right-click your Discord server icon.
2. Click **Copy Server ID**.

Your configuration will look similar to:

```lua
GuildID = "123456789012345678"
```

Replace the example number with your actual server ID.

***

## 6. Find Your Discord Role IDs

The duty systems use Discord Role IDs to determine which players have permission to use specific departments or features.

With Developer Mode enabled:

1. Open your Discord server.
2. Go to **Server Settings → Roles**.
3. Right-click the role you want to use.
4. Select **Copy Role ID**.

For example:

```lua
LEO = "123456789012345678"
```

You can create different roles for different departments.

Example:

```lua
Departments = {
    BCSO = {
        RoleID = "123456789012345678"
    },

    LSPD = {
        RoleID = "234567890123456789"
    },

    SAST = {
        RoleID = "345678901234567890"
    }
}
```

Use the actual Role IDs from your Discord server.

***

## 7. Configure the Script

Once you have your Guild ID, Bot Token, and Role IDs, enter them into the script's configuration.

A typical configuration will look similar to:

```lua
Discord = {
    BotToken = "YOUR_BOT_TOKEN",
    GuildID = "YOUR_GUILD_ID",

    Roles = {
        BCSO = "YOUR_BCSO_ROLE_ID",
        LSPD = "YOUR_LSPD_ROLE_ID",
        SAST = "YOUR_SAST_ROLE_ID"
    }
}
```

**The exact configuration structure may differ between X1Studios Duty System versions. Always use the configuration structure included with your specific release.**

***

## 8. Discord Role Hierarchy

Make sure the bot's role is positioned correctly in your Discord server's role hierarchy.

Go to:

**Server Settings → Roles**

Then move the bot's role above any roles that the bot needs to interact with.

For example:

```
Administrator
Bot
BCSO
LSPD
SAST
Civilian
```

The bot cannot manage or interact with roles positioned above its own role.

***

## 9. Restart Your FiveM Server

After completing the configuration:

1. Save your configuration file.
2. Make sure the Discord bot is online.
3. Make sure the Guild ID is correct.
4. Make sure all Role IDs are correct.
5. Restart your FiveM server/resource.

Players should now be checked against their Discord roles when using the duty system.

***

## Troubleshooting

#### The bot is offline

Check that:

* The Bot Token is correct.
* The bot has been invited to your server.
* The Discord application still has an active bot.
* You have not regenerated the token without updating your configuration.

#### Players cannot access a department

Check that:

* The player has the correct Discord role.
* The Role ID in the configuration is correct.
* The Guild ID is correct.
* The bot can access server members.
* Server Members Intent is enabled.

#### "Invalid Token" or authentication errors

Your Bot Token is incorrect, expired, or has been regenerated.

Go to the Discord Developer Portal and generate a new token, then update your configuration.

#### Role verification is not working

Double-check the following:

```
Guild ID
↓
Discord Bot
↓
Server Members Intent
↓
Discord Role ID
↓
Player's Discord Role
```

All five need to be configured correctly for Discord role verification to work.

***

### Security Warning

**NEVER share your Discord Bot Token.**

Your Bot Token provides access to your Discord bot and should be treated like a password.

If you are uploading your resource to GitHub or sharing your configuration with someone else, remove your real token first.

Use:

```lua
BotToken = "YOUR_BOT_TOKEN"
```

instead of your actual token.

If your token is accidentally leaked, immediately regenerate it through the Discord Developer Portal.
