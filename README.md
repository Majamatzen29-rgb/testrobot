# TestRobot

**Advanced AI Test Dummy & Robot Testing Environment for FiveM**

TestRobot is a powerful FiveM testing resource designed for developers and server owners who want to create, control, test, fight, talk to, equip, drive, and interact with AI test characters.

Each AI can have its own **ID, name, personality, rules, weapons, inventory, health, armor, vehicle, and behavior**.

---

## Features

* Up to **100 active AI**
* Male AI
* Female AI
* Robot AI
* Unique AI IDs
* Unique AI names
* Individual personalities
* Individual rules
* Individual inventories
* Weapons and ammunition
* AI looting
* AI health and armor
* AI statistics
* AI conversations
* AI behavior system
* AI combat testing
* AI vehicles
* AI driving
* AI animations
* AI targeting
* Owner-only controls
* NUI control menu
* Framework detection
* Optional inventory integrations
* Optional target integrations
* Optional external AI provider
* Optional voice system
* Webhook logging
* Server-side security
* Performance optimized for up to 100 AI

---

# Installation

Follow these steps carefully.

## 1. Download TestRobot

Download the TestRobot ZIP from this GitHub repository.

When you download it, open the first ZIP.

Inside the first ZIP you may see:

```text
TestRobot-Main
```

Open `TestRobot-Main`.

---

## 2. Open the second ZIP

Inside `TestRobot-Main`, there is another ZIP file.

**Open that ZIP file.**

Inside the second ZIP you will find:

```text
TestRobot
```

Open the `TestRobot` folder.

---

## 3. Find the actual resource

Inside the `TestRobot` folder you should see:

```text
TestRobot/
├── fxmanifest.lua
├── config.lua
├── client.lua
├── server.lua
├── README.md
└── html/
    ├── index.html
    ├── style.css
    └── script.js
```

**This is the folder you need to install.**

You need the `TestRobot` folder that contains `fxmanifest.lua`.

---

## 4. Put TestRobot into your server

Take the actual `TestRobot` folder and put it inside your FiveM server's resources directory.

For example:

```text
resources/
└── [local]/
    └── TestRobot/
        ├── fxmanifest.lua
        ├── config.lua
        ├── client.lua
        ├── server.lua
        ├── README.md
        └── html/
            ├── index.html
            ├── style.css
            └── script.js
```

Do **not** put the outer `TestRobot-Main` folder in your resources folder if it only contains the second ZIP.

You need the actual resource folder containing:

* `fxmanifest.lua`
* `config.lua`
* `client.lua`
* `server.lua`

---

## 5. Configure the owner

Open:

```text
TestRobot/config.lua
```

The owner license is configured there.

```lua
Config.OwnerLicense = "license:f9cb3badb8434d9d84217f8e11027096dc0819c"
```

The owner name is:

**Captain Jack**

The owner license must remain in `config.lua`.

Do **not** put the owner license in:

* `server.cfg`
* `client.lua`
* public documentation
* client-side NUI code

The owner permission check is performed server-side.

---

## 6. Add TestRobot to server.cfg

Open your `server.cfg`.

Add:

```cfg
ensure TestRobot
```

---

## 7. Start TestRobot

Restart your FiveM server.

You can also start it from the server console:

```text
ensure TestRobot
```

---

## 8. Test the resource

Join your server using the owner account.

Try:

```text
/spawnrobot
```

Open the menu:

```text
/menu
```

You can also test:

```text
/spawnmale
/spawnfemale
/spawnrobotarmed
```

---

# Supported Frameworks

TestRobot supports:

* Qbox
* QBCore
* ESX Legacy
* Standalone FiveM/CFX

Framework detection is automatic.

You do not need to manually select a framework.

Optional integrations can also be detected when available:

* `ox_lib`
* `ox_target`
* `qb-target`
* `ox_inventory`

These integrations are optional.

---

# Owner Access

TestRobot is designed as an owner-only testing environment.

Owner:

**Captain Jack**

The owner license is stored in:

```text
config.lua
```

Every protected command and server event performs an owner permission check.

Unauthorized users receive:

```text
You don't have permission to use this. Owner: Captain Jack.
```

The license is never sent to players.

---

# AI Limit

TestRobot supports a maximum of:

**100 active AI**

This limit applies to all AI types combined.

For example:

```text
50 Male
25 Female
25 Robot
----------------
100 / 100
```

When the maximum is reached:

```text
You cannot spawn anymore. Delete a robot and spawn again, or try again next time.
```

The limit is enforced server-side.

---

# AI Types

TestRobot supports three main AI types.

### Male

Male AI receive their own:

* ID
* Name
* Personality
* Rules
* Inventory
* Weapons
* Health
* Armor
* Behavior

### Female

Female AI receive their own:

* ID
* Name
* Personality
* Rules
* Inventory
* Weapons
* Health
* Armor
* Behavior

### Robot

Robot AI receive their own:

* ID
* Name
* Personality
* Rules
* Inventory
* Weapons
* Health
* Armor
* Behavior

---

# AI Names

Every AI receives an individual name.

Examples:

```text
Johnny
Joe
Jack
James
Michael
Daniel
Maya
Sarah
Emma
Sophie
```

Robot names can also be configured.

Each active AI has a unique identity.

Example:

```text
AI 1 — Johnny
AI 2 — Maya
AI 3 — Unit-03
```

---

# Spawn Commands

```text
/spawnrobot
/spawnrobot [amount]

/spawnmale
/spawnmale [amount]

/spawnfemale
/spawnfemale [amount]

/spawnrobotarmed
```

If no amount is specified, one AI is spawned.

AI spawn near the owner's current location.

Multiple AI use safe spawn offsets.

---

# AI Selection

Select an AI with:

```text
/robotselect [id]
```

Example:

```text
/robotselect 5
```

The selected AI becomes the target for individual commands.

The main menu also displays all active AI.

---

# Delete AI

Delete the selected AI:

```text
/robotdelete
```

Delete a specific AI:

```text
/robotdelete [id]
```

Alternative command:

```text
/delete robot [id]
```

Delete all AI:

```text
/deleteall
/deleteallrobots
/robotsdeleteall
```

When deleting all AI, associated test vehicles are also cleaned up.

A confirmation can be used before deleting all AI.

---

# Main Menu

Open the main menu:

```text
/menu
```

or:

```text
/robotmenu
```

The menu contains sections for:

* Robots
* Control
* AI Behavior
* Rules
* Weapons
* Inventory
* Health
* Armor
* Animations
* Vehicles
* Statistics
* Talk
* Personality
* Settings

The menu displays:

```text
Active AI: X / 100
```

---

# AI Behavior

AI can use different behavior states:

* Idle
* Following
* Guarding
* Wandering
* Fleeing
* Searching
* Combat
* Taking Cover
* Driving
* Passenger
* Talking
* Commanding
* Dead
* Injured
* Frozen
* Passive

Available modes include:

* Passive
* Armed
* Hostile
* Invincible
* Frozen
* Mobile
* Melee
* Shooter
* Guard
* Flee
* Follow
* Wander

---

# Behavior Commands

```text
/robotfollow
/robotstop
/robotfollowall
/robotstopall

/robotattack
/robotpassive
/robotpassiveall

/robotguard
/robotflee

/robotfreeze
/robotunfreeze
/robotfreezeall
/robotunfreezeall

/robotwander
/robotstand
/robotchase

/robotcombat
/robotnocombat

/robotmode
```

AI behavior takes into account:

* Current command
* AI rules
* Personality
* Health
* Armor
* Weapon
* Ammunition
* Owner location
* Current target
* Threats
* Vehicle status
* Current task
* Conversation

The behavior system is designed to avoid unnecessary per-frame processing.

---

# AI Rules

Each AI has its own rules.

Default rules include:

```text
Do not attack owner: ON
Obey owner: ON
Randomly attack people: OFF
Randomly steal vehicles: OFF
Randomly attack civilians: OFF
Use weapons without command: OFF
Leave assigned area: OFF
Speak when spoken to: ON
Follow direct commands: ON
```

Commands:

```text
/robotrules
/robotrule [rule]
```

Rules have priority over personality.

Rules cannot execute arbitrary Lua code or arbitrary commands.

---

# AI Personalities

Available personalities include:

* Friendly
* Professional
* Military
* Civilian
* Aggressive
* Coward
* Guard
* Funny
* Developer
* Neutral

Personality can influence:

* Dialogue
* Reactions
* Preferences
* Tolerance
* Combat behavior when allowed

Rules always override personality behavior.

---

# Reactions

AI can react to situations such as:

* Being pushed
* Being bumped
* Shots fired nearby
* Being interrupted
* Confusing commands
* Repeated commands

Example reactions include:

```text
What the hell is going on?

Captain Jack, what are you doing?

Seriously?

Can you make up your mind?

Okay... I don't know what you want me to do.

That was unnecessary.

Are you testing me again?
```

AI reactions depend on their personality and current situation.

A reaction does not automatically make an AI violent.

The AI's rules determine what it is allowed to do.

Behavior states such as Calm, Confused, Annoyed, Alert, Afraid, Happy, Focused, and Angry are gameplay behavior states.

---

# Weapons

Supported weapon categories include:

* Pistol
* Combat Pistol
* Heavy Pistol
* AP Pistol
* Micro SMG
* SMG
* Assault SMG
* Assault Rifle
* Carbine Rifle
* Special Carbine
* Bullpup Rifle
* Pump Shotgun
* Combat Shotgun
* Assault Shotgun
* Heavy Shotgun
* Sniper Rifle
* Heavy Sniper
* Marksman Rifle
* Knife

Commands:

```text
/robotweapon
/robotpistol
/robotsmg
/robotrifle
/robotshotgun
/robotsniper
/robotknife
/robotdisarm
/robotarmall
/robotdisarmall
```

AI weapon behavior considers:

* Range
* Ammunition
* Reloading
* Cover
* Current mode
* Rules
* Threats

Passive AI should not randomly shoot.

---

# AI Inventory & Looting

Each AI can have its own inventory.

Weapons and ammunition can be transferred through supported inventory systems.

Supported integrations can include:

* `ox_inventory`
* Qbox/QBCore inventory systems
* ESX inventory systems
* Standalone fallback

The resource must use actual inventory data where supported.

It should not create fake infinite inventory items or duplicate ammunition.

---

# Looting Dead AI

When an AI is killed, its inventory remains available on the corpse.

The owner can loot the dead AI.

Items can include:

* Weapons
* Ammunition
* Other configured loot/items

The AI's inventory remains associated with that AI until it is looted or the AI is cleaned up.

When supported, target integrations can provide:

```text
Give Weapon
Give Ammo
Inspect AI
Talk
Command
Loot
```

---

# Health & Armor

Commands:

```text
/setrobothealth [amount]
/setrobotarmor [amount]

/robothealth
/robotarmor

/giverobothealth

/robothealall
/resetrobot
```

AI statistics can track:

* Current health
* Maximum health
* Armor
* Hits
* Total damage
* Last damage
* Last weapon
* Last bone
* Last attacker
* Death count
* Current state

---

# Statistics

Open statistics with:

```text
/robotstats
```

Reset statistics:

```text
/resetrobotstats
```

Respawn:

```text
/robotrespawn
```

---

# Animations

Commands:

```text
/robotanim idle
/robotanim wave
/robotanim sit
/robotanim kneel
/robotanim surrender
/robotanim injured
/robotanim stop
```

---

# Vehicles

Each AI can have its own test vehicle.

Commands:

```text
/robotvehicle
/robotdrive
/robotdrivewall
/robotvehicleoff
/robotexitvehicle

/robotdriveforward
/robotreverse
/robotbrake
/robotcrash
```

AI can:

* Enter vehicles
* Exit vehicles
* Drive
* Follow
* Stop
* Reverse
* Brake
* Perform controlled crash tests

AI vehicles are not randomly driven around the entire server.

---

# Natural Language Commands

TestRobot supports safe predefined commands such as:

```text
Follow me.
Come with me.
Stay here.
Stop following me.
Get in the car.
Get out of the car.
Drive forward.
Stop the car.
Run away.
Go over there.
Guard this place.
Use the shotgun.
Put your gun away.
Sit down.
Stand up.
```

Natural-language commands are mapped only to safe predefined actions.

They cannot execute arbitrary Lua code.

---

# Talking

Open the talk system:

```text
/talk
```

Each AI can maintain its own short-term conversation history.

Conversation history can be cleared.

---

# Optional AI Provider

External AI integration is optional.

Default configuration:

```lua
Config.AI = {
    Enabled = false,
    Provider = "none",
    Endpoint = "",
    ApiKey = "",
    Model = "",
    MaxTokens = 300
}
```

The resource works without an external AI provider.

API keys must remain server-side.

AI responses cannot directly execute code.

Only safe predefined actions are allowed, including:

```text
FOLLOW
STOP
ATTACK
PASSIVE
GUARD
FLEE
WANDER
ENTER_VEHICLE
EXIT_VEHICLE
DRIVE
BRAKE
REVERSE
WEAPON_SELECT
ANIMATION
```

---

# Optional Voice

Voice configuration:

```lua
Config.Voice = {
    Enabled = false,
    Provider = "none",
    Endpoint = "",
    ApiKey = ""
}

Config.VoiceOutput = false
```

Voice functionality can use:

```text
FiveM voice/microphone
        ↓
Speech-to-text
        ↓
Safe command parser
        ↓
AI action
```

Voice is optional and the resource works without it.

API keys are server-side only.

---

# Target Integration

When available, TestRobot can integrate with:

```text
ox_target
qb-target
```

Possible options include:

```text
Give Weapon
Give Ammo
Inspect AI
Talk
Command
Loot
```

Slash commands and the main menu remain available without a target system.

---

# Framework Integration

TestRobot can automatically detect:

```text
qbx_core
qb-core
es_extended
```

It also supports standalone FiveM servers.

---

# Testing Exports

Other resources can use TestRobot for testing.

Example:

```lua
local ped, netId, dist = exports['testrobot']:GetNearestRobot(5.0)

local list = exports['testrobot']:GetRobotList()

local ped, netId = exports['testrobot']:GetRobotPed(1)

local isRobot, id, name = exports['testrobot']:IsTestRobot(entity)
```

These exports can be used to test:

* Target systems
* Police menus
* Weapon menus
* Interaction systems
* Inventory systems
* AI-related scripts
* Other FiveM resources

---

# Webhook Logging

TestRobot can optionally send server-side logs to a Discord webhook.

Configuration:

```lua
Config.Webhook = {
    Enabled = false,
    URL = "",
    Name = "Test Robot",
    Avatar = ""
}
```

Possible events include:

* AI spawned
* AI deleted
* AI armed
* AI disarmed
* AI killed
* AI revived
* Health changed
* Armor changed
* Weapon changed
* Mode changed
* Vehicle created
* Vehicle removed
* Loot activity

The webhook URL must remain server-side.

---

# Configuration

Example default configuration:

```lua
Config.MaxRobots = 100

Config.RobotHealth = 1000
Config.RobotMaxHealth = 1000
Config.RobotArmor = 100

Config.SpawnDistance = 3.0

Config.DefaultWeapon = "WEAPON_PISTOL"
Config.DefaultAmmo = 100

Config.WeaponAccuracy = 60
Config.CombatAbility = 2

Config.DetectionDistance = 100.0

Config.VehicleModel = "blista"

Config.DefaultRobotPersonality = "Professional"

Config.AI = {
    Enabled = false,
    Provider = "none",
    Endpoint = "",
    ApiKey = "",
    Model = "",
    MaxTokens = 300
}

Config.Voice = {
    Enabled = false,
    Provider = "none",
    Endpoint = "",
    ApiKey = ""
}

Config.VoiceOutput = false

Config.Debug = false

Config.Webhook = {
    Enabled = false,
    URL = "",
    Name = "Test Robot",
    Avatar = ""
}
```

Other settings can be configured for:

* Names
* Personalities
* Rules
* Weapons
* Inventory
* Loot
* Vehicles
* AI intervals
* Behavior
* Debugging

---

# Complete Commands

```text
/testrobot on
/testrobot off

/spawnrobot [amount]
/spawnmale [amount]
/spawnfemale [amount]
/spawnrobotarmed

/menu
/robotmenu
/robotselect [id]

/deleteall
/deleteallrobots
/robotsdeleteall
/delete robot [id]

/robotdelete
/robotdelete [id]

/robotrespawn
/giverobothealth
/robothealall
/resetrobot

/robotfollow
/robotstop
/robotfollowall
/robotstopall

/robotattack
/robotpassive
/robotpassiveall

/robotguard
/robotflee

/robotfreeze
/robotunfreeze
/robotfreezeall
/robotunfreezeall

/setrobothealth [amount]
/setrobotarmor [amount]

/robothealth
/robotarmor

/robotweapon
/robotpistol
/robotsmg
/robotrifle
/robotshotgun
/robotsniper
/robotknife
/robotdisarm

/robotarmall
/robotdisarmall

/robotanim idle
/robotanim wave
/robotanim sit
/robotanim kneel
/robotanim surrender
/robotanim injured
/robotanim stop

/robotvehicle
/robotdrive
/robotdrivewall
/robotvehicleoff
/robotexitvehicle
/robotdriveforward
/robotreverse
/robotbrake
/robotcrash

/robotwander
/robotstand
/robotchase
/robotcombat
/robotnocombat
/robotmode

/robotrules
/robotrule [rule]

/robotstats
/resetrobotstats

/talk

/testrobotwebhook
```

---

# Security

TestRobot uses server-side security checks.

Protected functionality validates:

* Owner permissions
* AI IDs
* Spawn amounts
* Weapons
* Ammunition
* Health
* Armor
* Modes
* Rules
* Commands
* Server events

The resource does not allow players to execute arbitrary Lua code through AI commands.

---

# Performance

TestRobot is designed to support up to **100 active AI**.

The resource avoids unnecessary expensive per-frame processing wherever possible.

AI behavior uses lightweight decision logic based on the current situation.

When the resource stops, spawned AI and associated test vehicles are cleaned up.

---

# Troubleshooting

### TestRobot does not start

Check that the folder containing `fxmanifest.lua` is inside your resources directory.

Correct:

```text
resources/[local]/TestRobot/fxmanifest.lua
```

Make sure `server.cfg` contains:

```cfg
ensure TestRobot
```

---

### The resource says I do not have permission

Check the owner license in:

```text
TestRobot/config.lua
```

Make sure:

```lua
Config.OwnerLicense = "license:f9cb3badb8434d9d84217f8e11027096dc0819c"
```

matches the owner's FiveM license.

---

### The commands do not work

Make sure the resource is running:

```text
ensure TestRobot
```

Then restart the resource or restart the server.

---

### I downloaded the wrong folder

Remember the ZIP structure:

```text
First ZIP
    ↓
TestRobot-Main
    ↓
Second ZIP
    ↓
TestRobot
    ↓
fxmanifest.lua
```

The **`TestRobot` folder containing `fxmanifest.lua`** is the folder that belongs in your resources directory.

---

# File Structure

The final resource should look like:

```text
TestRobot/
├── fxmanifest.lua
├── config.lua
├── client.lua
├── server.lua
├── README.md
└── html/
    ├── index.html
    ├── style.css
    └── script.js
```

---

# Quick Start

```text
1. Download TestRobot
2. Open the first ZIP
3. Open TestRobot-Main
4. Open the second ZIP
5. Open TestRobot
6. Take the TestRobot folder containing fxmanifest.lua
7. Put it in resources/[local]/
8. Add "ensure TestRobot" to server.cfg
9. Restart the server
10. Join as Captain Jack
11. Use /spawnrobot
12. Use /menu
```

---

# Credits

**Resource:** TestRobot
**Author:** Captain Jack
**Version:** 1.0.0
**Maximum Active AI:** 100

TestRobot is designed as an advanced testing environment for FiveM developers and server owners.
