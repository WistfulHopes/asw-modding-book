# Using Blender

<hr>

**Note that this document will not cover the basics of Blender.**

Several tools were created to make Blender compatible with modding Arc System Works games.

## Modified gltf plugin

[Download the modified gltf plugin](https://cdn.discordapp.com/attachments/856713078128771112/1074927094385094666/io_scene_gltf2_ue4.zip)

Fire up Blender, go to your Preferences > Add-ons. Type `gltf` into the search bar. If it doesn't show up, make sure you're in the 'Official' tab.

Disable it. Nuke it. Throw it out the window.

Now close Blender, and extract `io_scene_gltf2_ue4.zip` into your Blender addons directory.
For Windows, this can be found in:

`%appdata%\Blender Foundation\Blender\` `<your Blender version>` `\scripts\addons\`

Next, fire up Blender and go back to the Add-ons menu. If all went well, you'll find a new entry in there called `Import-Export: glTF 2.0 format - For Unreal Engine Modding`. Simply enable it, and you're good to go.

You can now import gltf meshes & skeletons via `File > Import > glTF 2.0 (.glb/.gltf) - Unreal`.

## Aerthas' custom materials & shaders

[Download BLENDER-Arc-System-Works-Shader](https://github.com/Aerthas/BLENDER-Arc-System-Works-Shader)

Not strictly needed for modding these games, but superb for preview models and textures within Blender itself.

Aerthas made a ton of practical videos on how to actually use his shader. Although the YouTube playlist is linked on that very Github page, [don't mind if we link it here as well](https://www.youtube.com/playlist?list=PLCkHUM_E60CSi1HowXR3v4uVWNqUDsl9l).

## Scripts

[Browse Arc-Sys-scripts](https://github.com/SaitsuP/Arc-Sys-scripts)

The most useful scripts have their own [wiki pages](https://github.com/SaitsuP/Arc-Sys-scripts/wiki), which also go into detail on how to use them.

## A note on Blender FBX export into UE4

Vanilla Blender FBX export is kinda icky. If you're willing to pay up, consider [Better Fbx Importer & Exporter](https://blendermarket.com/products/better-fbx-importer--exporter) instead.
