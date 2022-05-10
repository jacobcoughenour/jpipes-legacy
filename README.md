
---
# ⚠️ NOTICE: This plugin is no longer maintained. 
# 👉 **Use [syncPipes](http://umod.org/plugins/sync-pipes) by [Joe90](http://umod.org/user/Joe90).** *"It's way better" - TheGreatJ*
---


JPipes adds pipes that transfer items between deployables with limitless automation possibilities.

![](https://i.imgur.com/BeYWVPO.png?1)

[Planned Features / TODO List](https://trello.com/b/oXiOcmBo)

## Automate With Pipes

* Item Sorting
* Fueling Furnaces, Mining Quarries, and Pump Jacks
* Storing water from Catchers in Barrels
* Recycling items
* Refilling Turrets
* Refining Crude Oil
* Raiding
* Becoming a God

[![](https://i.imgur.com/4M8rCKjt.jpg)](https://i.imgur.com/4M8rCKj.jpg)
[![](https://i.imgur.com/jioPhalt.jpg)](https://i.imgur.com/jioPhal.jpg)
[![](https://i.imgur.com/SxVYu2Rt.jpg)](https://i.imgur.com/SxVYu2R.jpg)
[![](https://i.imgur.com/xD5GmFEt.jpg)](https://i.imgur.com/xD5GmFE.jpg)

## Creating Pipes

Press P or do the `/p` command in chat then select the first and second containers by hitting them with a Hammer.

## Pipe Menu

Each pipe has its own settings menu that can be opened by hitting it with a Hammer

[![pipe menu](https://i.imgur.com/mSK2miqt.jpg?11)](https://i.imgur.com/mSK2miq.jpg)

* **Turn On / Turn Off** - enables or disables the pipe from transferring items/liquid
* **Auto Starter** - after a pipe sends an item to a furnace, recycler, refinery, mining quarry, or pump jack, it will attempt to start it
* **Change Direction** - Makes the items go the other direction through the pipe
* **Multi Stack / Single Stack** - Multi Stack mode allows the pipe to create multiple stacks of the same item.  Single Stack mode prevents the pipe from creating more than one stack of an item.  Single Stack mode is mostly just for fueling furnaces to leave room for other items.
* **Item Filter** - This opens a small stash that you can place items in.  When items are in the filter, only those items will be transferred through the pipe.  When the filter is empty, all items will be transferred.  The items you place in the filter are not removed from your inventory and when you take items from the filter it will not add it to your inventory.

## Upgrading

[![](https://i.imgur.com/aO1bRXit.jpg)](https://i.imgur.com/aO1bRXi.jpg)
* Use a hammer and upgrade the pipe just like any other building
* Each upgrade level increases the pipe's flow rate and Item Filter size.  The pipe's current flow rate is displayed in its menu.

## Permissions

* `jpipes.use` - allows playert to create and modify pipes
* `jpipes.admin` - overrides perm level limits and building privilege

## Chat Commands

* `/p` -  start or stop placing a pipe
* `/p c`, `/pcopy`, or `/p copy` - copy pipe settings from one pipe to another
* `/p r`, `/premove`, or `/p remove` - remove pipe with hammer
* `/p s`, `/pstats`, or `/p stats` - pipe status with how many pipes you are using
* `/p h`, `/phelp`, or `/p help` - JPipes in-game help

## Configuration

* **drawflowarrows** - show flow arrows on the sides of pipes when you hold a hammer[/I]
* **animatearrows** - animated flow arrows (causes lag)
* **maxpipedist** -max length of the pipe
* **minpipedist** - min length of the pipe
* **pipecommandprefix** - prefix for chat commands. Ex. "jp" = /jp copy
* **pipehotkey** - hotkey for creating pipe
* **updaterate** - delay (in seconds) for pipe update function.  Increase this if you are running into lag issues with this plugin.
* **flowrates** - flowrates (in items/sec) for each upgrade level.
* **filtersizes** - slots for each upgrade level.  0 = disable filter. 30 is the max.
* **nodecay** - disables decay damage on pipes.
* **xmaslights** - enable xmas lights on pipes
* **permlevels** - (see the Perm Levels section below)

# Perm Levels (optional)

The **permlevels** config option allows server owners to set pipe limits for each player through permissions.  This can be used with various reward plugins that can grant and revoke permissions.

**Configuration Example:**
```json
{
  ...
  "permlevels": {
      "first":{
          "pipelimit":3
      },
      "second":{
          "upgradelimit":1
      },
      "third":{
          "pipelimit":-1,
          "upgradelimit":3
      }
   },
  ...
}
```

The permlevels are registered as oxide permissions in this format  

jpipes.level.*levelname*
    
So with the configuration example above, the permissions would be:

jpipes.level.first  
jpipes.level.second  
jpipes.level.third

## Notes

* Setting a limit to -1 makes it infinite
* When multiple permlevels are granted to a single player, the highest value is used.  So from the example above, if a player has the "first", "second", and "third" permlevels, their "pipelimit" would be -1 and "upgradelimit" would be 3.
* *upgradelimit* corresponds to the order of building grades where 0 = Twig, 1 = Wood, 2 = Stone, 3 = Metal.  Any other value is defaulted to -1.

## Other Features

* Pipes will auto-filter items biased on their destination container.  So only fuel/cook-able items will be transported to ovens, recyclable to recycler, etc.
