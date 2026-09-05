# Installation

## Installation

### Step 1 — Download

Download the latest version of the **X1Studios Advanced Duty System**.

Extract the resource into your server's resources directory.

Example:

```
resources/
└── [x1studios]/
    └── X1S-AdvDutySystem/
```

***

### Step 2 — Configure

Open the configuration files included with the resource.

Configure your:

* Departments
* Department names
* Ranks
* Callsigns
* Discord roles
* ACE permissions
* Supervisor permissions
* Duty blips
* Discord webhooks
* 911 settings
* Panic settings
* Notifications

***

### Step 3 — Add to Server Configuration

Add the resource to your `server.cfg`:

```
ensure X1S-AdvDutySystem
```

Make sure the resource starts after any resources that your server configuration specifically requires it to start after.

***

### Step 4 — Configure Discord ACE Permissions

Configure the appropriate Discord ACE permissions for your server.

Assign the required Discord roles to your personnel and ensure the corresponding ACE permissions are configured correctly.

Once configured, authorized personnel will be able to access the appropriate duty and supervisor features.

***

## Configuration

The system is designed to be highly configurable.

Common configuration areas include:

#### Departments

Create additional departments and customize their settings.

#### Ranks

Create custom ranks for each department.

Example:

```
Cadet
Deputy
Corporal
Sergeant
Lieutenant
Captain
Sheriff
```

#### Callsigns

Configure available callsign formats or options for department personnel.

#### Permissions

Configure ACE permissions for restricted features.

#### Discord Webhooks

Add Discord webhook URLs for system logging and 911 alerts.

#### Blips

Configure duty and emergency blip behavior.

#### Notifications

Configure how system notifications are displayed.

***

## Troubleshooting

### Duty Blip Is Not Appearing

Check the following:

1. Verify the player successfully went on duty.
2. Verify duty blips are enabled in the configuration.
3. Verify the department has a valid blip configuration.
4. Check the server console for errors.
5. Restart the resource after making configuration changes.

***

### Supervisor Menu Does Not Open

Verify that:

1. The player has the required Discord role.
2. Discord ACE permissions are configured correctly.
3. The supervisor permission is assigned to the correct ACE group.
4. The Discord integration/resource required for your permission setup is running.

***

### 911 Calls Are Not Being Received

Check:

1. The receiving officer is on duty.
2. The officer has the appropriate department access.
3. 911 functionality is enabled.
4. The resource is running without errors.
5. The configured permissions and department settings are correct.

***

### Discord Logs Are Not Sending

Check:

1. The webhook URL is correct.
2. The webhook has not been deleted.
3. Discord is allowing messages from the webhook.
4. The webhook is configured in the correct configuration file.
5. Your server console does not show webhook-related errors.
