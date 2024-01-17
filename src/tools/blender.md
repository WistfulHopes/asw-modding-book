# Using Blender

<hr>

**Note that this document will not cover the basics of Blender.**

Several tools were created to make Blender compatible with modding Arc System Works games.

## Modified glTF plugin

[Download the modified glTF plugin](https://cdn.discordapp.com/attachments/856713078128771112/1074927094385094666/io_scene_gltf2_ue4.zip)

Fire up Blender, go to your Preferences > Add-ons. Type `gltf` into the search bar. If it doesn't show up, make sure you're in the 'Official' tab.

Disable it. Nuke it. Throw it out the window.

Now close Blender, and extract `io_scene_gltf2_ue4.zip` into your Blender addons directory.
For Windows, this can be found in:

`%appdata%\Blender Foundation\Blender\` `<your Blender version>` `\scripts\addons\`

Next, fire up Blender and go back to the Add-ons menu. If all went well, you'll find a new entry in there called `Import-Export: glTF 2.0 format - For Unreal Engine Modding`. Simply enable it, and you're good to go.

You can now import glTF meshes & skeletons via `File > Import > glTF 2.0 (.glb/.gltf) - Unreal`.

## Aerthas' custom materials & shaders

[Download BLENDER-Arc-System-Works-Shader](https://github.com/Aerthas/BLENDER-Arc-System-Works-Shader)

While not strictly needed for modding, the shader is highly recommended for previewing models and textures within Blender itself.

Aerthas made a ton of practical videos on how to use his shader. [Here is a link to a playlist containing said videos](https://www.youtube.com/playlist?list=PLCkHUM_E60CSi1HowXR3v4uVWNqUDsl9l).

## Scripts

[Browse Arc-Sys-scripts](https://github.com/SaitsuP/Arc-Sys-scripts)

The most useful scripts have their own [wiki pages](https://github.com/SaitsuP/Arc-Sys-scripts/wiki), which also go into detail on how to use them.

## A note on Blender FBX export into UE4

The default Blender FBX exporter, while usable, is not preferred for Unreal Engine 4 modding. If you're willing to pay up, consider [Better FBX Importer & Exporter](https://blendermarket.com/products/better-fbx-importer--exporter) instead.

If you are modding Guilty Gear -Strive- or a game newer than it, there is also [Epic Games' very own Send to Unreal addon](https://github.com/EpicGames/BlenderTools/releases/tag/20220216152539). **The linked release is the last one that works on UE4.25. Newer releases only support UE4.27 and above, and the most recent releases only supports UE5.** 

Note that you must have connected your GitHub account to your Epic Games account in order to view this page. [Click here for more information.](https://www.epicgames.com/help/en-US/epic-accounts-c5719348850459/connected-accounts-c5719351300507/how-do-i-link-my-unreal-engine-account-with-my-github-account-a5720369784347?sessionInvalidated=true)

If you are *not* using the Better FBX addon, there is one step that must be followed in order to export an FBX to Unreal:
- The Armature for your model *must* be named Armature. **If it is named anything else, skeletal mesh imports will not animate correctly.**

Additionally, if you are not using the Send to Unreal addon, there is one more step that must be undertaken:
- Under the Scene tab of the Properties menu, set the Unit Scale to 0.01. You will also need to scale your model proportionately (100 times).