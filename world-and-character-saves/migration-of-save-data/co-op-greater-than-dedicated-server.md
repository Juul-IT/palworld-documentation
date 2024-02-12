# Co-op -> Dedicated server

Prerequisites:

* Install the dependencies [above](https://github.com/xNul/palworld-host-save-fix#usage).
* The dedicated server is installed, running, and you're able to join it.
* Follow the workaround [below](https://github.com/xNul/palworld-host-save-fix#guild-bug) for the \[Guild bug] in co-op before moving the save.
* If you have a Viewing Cage, follow the workaround [below](https://github.com/xNul/palworld-host-save-fix#viewing-cage-bug) for the \[Viewing Cage bug] in co-op before moving the save.

Steps:

1. Copy your desired save's folder from `C:\Users\<username>\AppData\Local\Pal\Saved\SaveGames\<random_numbers>` to your dedicated server at `PalServer\Pal\Saved\SaveGames\0`.
2. In the `PalServer\Pal\Saved\Config\WindowsServer\GameUserSettings.ini` file, change the `DedicatedServerName` to match your save folder's name. For example, if your save folder's name is `2E85FD38BAA792EB1D4C09386F3A3CDA`, the `DedicatedServerName` changes to `DedicatedServerName=2E85FD38BAA792EB1D4C09386F3A3CDA`.
3. Delete `PalServer\Pal\Saved\SaveGames\0\<your_save_here>\WorldOption.sav` to allow modification of `PalWorldSettings.ini`. Players will have to choose their respawn point again, but nothing else is affected as far as I can tell.
4. Confirm you can connect to your save on the dedicated server and that the world is the one you want. You can connect to the dedicated server and check the world with a character that does not belong to the co-op host.
5. Afterwards, the co-op host must create a new character on the dedicated server. A new `.sav` file should appear in `PalServer\Pal\Saved\SaveGames\0\<your_save_here>\Players`.
6. The name of that new `.sav` file is the co-op host's new GUID. We will need the co-op host's new GUID for the script to work.
7. Shut the server down and then copy the entire save folder in the dedicated server at `PalServer\Pal\Saved\SaveGames\0\<your_save_here>` (it must be the save folder with the co-op host's new character!) into a temporary folder and remember the path for the temporary folder because it's needed to run the script.
8. **Make a backup of your save folder!** This is an experimental script and has known bugs so always keep a backup copy of your save folder.
9. Run the script using the command in the [Usage section](https://github.com/xNul/palworld-host-save-fix#usage) with the information you've gathered, using `00000000000000000000000000000001` as the co-op host's old GUID, and make sure to set `<guild_fix>` to `False`.
10. Copy the save folder from the temporary folder back to the dedicated server. Move the save folder you had in the dedicated server somewhere else or rename it to something different.
11. Start the server back up and have the co-op host join the server with their fixed character.
12. If, after 5 minutes of play, your Pals won't attack for you or do work in the base, follow the [\[Pal bug\] workaround](https://github.com/xNul/palworld-host-save-fix#pal-bug) to fix them.
