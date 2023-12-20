# Packaging your mod

First: the prerequisites. In order to package your mod, the folder hierarchy must follow the rule of `ModName\RED\Content\`, with the rest of the hierarchy matching the asset's original path.

As an example, if I am modding the asset sol_body in folder `RED\Content\Chara\SOL\Costume01\Mesh` and the mod is named LabcoatSol, I would need to have sol_body in `LabcoatSol\RED\Content\Chara\SOL\Costume01\Mesh`. Then, put sol_body.uasset *and* sol_body.uexp in that folder.

Then, you need a tool to package the mod. There is only one option I recommend for this: [Epic Games' own Unreal Pak tool](https://drive.google.com/file/d/1erwPVaAWp_9S0JzeM0aMR_NfHIcU6a4Z/view?usp=sharing). This specific version of Unreal Pak works on all Arc System Works games, though I can't guarantee it works on *all* Unreal Engine games.

Actually packaging your mod is quite simple: simply drag the mod folder onto the `UnrealPak-With-Compression.bat` file. It should spit out a file with the same name as the mod folder, but with the .pak extension.