# Installing your mod

Once your mod is packaged, you currently have two options for installing it:

1. Using Unverum. Press "Add Mods" at the top-right, then click "Create New Mod." Give it any name you wish, and after pressing Confirm, find the .pak you made in the previous step. Now, once you press Launch at the top-center, your mod will be used in-game. This method's main advantages are easy management of mods, and .sig files are generated for you. The main disadvantage is that Unverum is somewhat clunky by comparison to mod managers used by other communities, and a decent number of people choose to not use it altogether.

2. Manual installation. Navigate to your game's Steam installation directory, then to RED\Content\Paks. Create a new folder inside Paks with name `~mods` (remember the ~ symbol, it is important). You may now put the previously generated .pak inside this folder. The final step is to take a .sig file from the game's Paks folder, copy it into `~mods`, and rename it to have the same name as your mod. As an example, if you have a mod named `LabcoatSol.pak` for Guilty Gear -Strive-, you would take `pakchunk0-WindowsNoEditor.sig` from the Paks directory, copy it into `~mods`, and rename it to `LabcoatSol.sig`.

<div class="warning">

If you are modding Granblue Fantasy Versus: Rising (*not* the original Granblue Fantasy Versus), you will need to add `-fileopenlog` to the Steam launch options for the game. **Otherwise, your mods will not work.** [Here is the official Steam documentation on launch options.](https://help.steampowered.com/en/faqs/view/7D01-D2DD-D75E-2955)

</div>