# Using Blender

<hr>

**Note that this document will not cover the basics of Blender.**

Several tools were created to make Blender compatible with modding Arc System Works games.

## FModel with Arc System Works animation support

[Download the UEFormat addon](https://github.com/halfuwu/UEFormat/tree/master)
[Download the modified FModel with ArcSys animation support](https://github.com/WistfulHopes/FModel/releases/tag/arcsys)

FModel supports exporting models and animations to a new "UEFormat", which is more accurate than either PSK/PSA or glTF. To export to UEFormat, open FModel's settings, then click on the `Models` tab. Finally, set `Mesh Format` to `UEFormat (uemodel)`.

Now, you can right-click a model, animation, or folder containing either, and export the models/animations to UEFormat. The attached Blender addon can then import these.

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