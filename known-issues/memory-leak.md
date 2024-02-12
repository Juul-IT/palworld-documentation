# Memory leak

There are a few events which occur in the game, which are believed to cause memory leaks.

There are currently two ways to combat this.

* Set `bEnableInvaderEnemy=False` in your `PalWorldSettings.ini`
* Setup automated restarts for your server. SomeCurrent recommendations below, you will need to figure out what works best for you:
* 16GB RAM, 8 Users every 8 Hours.
* 32GB RAM, 16 Users Every 12 Hours
* 32GB RAM, 8 Users Every 24 Hours

Events believed to cause an issue:

* Joining Dungeons repeatedly
* Raid events
* Party Pals working on the base, they have been seen to "Move" items around but go out of bounds and then drop them repeaetedly. This leads to a large pile of resource in the Pals pathing.
