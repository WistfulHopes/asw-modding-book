# Extracting your mesh
*This section is under construction, and was written by @muuyo*

<hr>
<br>

You're looking to use either [Fmodel](/tools/fmodel.md), a more recent and (arguably) better piece of software for this (page linked)
or [Umodel](/tools/umodel.md), a less recent, clunkier, less easy-to-preview piece of software that I wouldn't recommend sticking with but is here for posterity.
Learn how to set each up at the links above.

There are many ways to skin this cat, but I will be covering the two methods that are most well known - Fmodel and Umodel.
Either way, mesh locations you'll want to look for:

- Character meshes are stored in a tree like `RED\Chara\ANJ\Costume01\Mesh`
- Character meshes *used for moves* are stored in places like `RED\Chara\ANJ\Common\Effect\Particles\ANJ_PTC01\Mesh`. This is much more trial and error, however most are named after their [animation IDs, linked here.](https://docs.google.com/spreadsheets/d/1qrsX0QnmltX6DumfoRX7a76uvRJNh4AfU3QFdtOkcYc/edit?usp=sharing) Warning, these are shared across every color on that character, just like normal mesh mods.
- Map meshes are stored in `RED\Map\Battle\` under their internal name - an index is [linked here.](https://docs.google.com/spreadsheets/d/1qrsX0QnmltX6DumfoRX7a76uvRJNh4AfU3QFdtOkcYc/edit?usp=sharing). This is slightly outdated, but you should be able to figure it out.


<br>
<hr>

## Fmodel
Set up Umodel using the tutorial [here](/tools/fmodel.md).

This is a newer method, however most likely much less of a pain to use, and more foolproof.
- Follow the steps in the [blender section for Fmodel](../tools/blender.md#fmodel-with-arc-system-works-animation-support) to download Fmodel and the Blender addon to accept .ueformat files
- Configure Fmodel (if you need to) using [the steps in Section 3.1](../tools/fmodel.md) to correctly open Strive's files
- Optionally, double click any file to preview it in Fmodel's viewer
- Right click any file in Fmodel, and export as a ueformat file as in the page linked in Step 1
<br>
<hr>

## Umodel
Set up Umodel using the tutorial [here](/tools/umodel.md).
- now, browse through the game's file trees to find whatever you wish to extract, then either right click the folder on the left and press Export folder content
- or, right click an individual file and do so. For more detailed overhaul-y mesh mods, I recommend exporting animations at this step as well, [explained in section 7,](/modding-animation/animation-intro.md) as having them in Blender will mean you don't have to extract the mesh again later - they're very useful for finding when and how your model **will** jank out.