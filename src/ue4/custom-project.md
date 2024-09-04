# Getting the project for your game

<hr>

The prebuilt custom projects provide all of the custom asset types the game supports, and for newer games, they even include many assets from the game, such as UI elements or data tables. 

Below are download links for each game:

- [Dragon Ball FighterZ custom project](https://drive.google.com/file/d/1-wjbe0aE4Xs8S7AunSB0XtAE-sSZsOnW/view?usp=sharing)
- The original Granblue Fantasy Versus does not have a custom project.
- Guilty Gear -Strive-'s custom project is bundled with the editor.
- [DNF Duel custom project](https://1drv.ms/u/s!ApT7KvOr_B0hgY3rUBgqs787KHi5_iY?e=xKuxrI)
- [Granblue Fantasy Versus Rising custom project](https://drive.google.com/file/d/1aA1WYxkxpOUpNqSi5kANLUhh4Ja7A_4l/view?usp=drive_link)

The Guilty Gear -Strive- custom project does not come with content by default. To get the content, you can copy `pakchunk0-WindowsNoEditor.pak` from your copy of Strive into `RED\Content\Paks`. If the Paks folder does not exist, create it.

Additionally, the Strive project may receive asset patches for certain assets. To use these, extract `GGSTContent_Patch.rar` into `RED`.

Once you have downloaded the correct project, extract it to your Unreal Projects directory. If you've run the editor before, you can usually find it at `Documents\Unreal Projects\`. **For Guilty Gear -Strive-, the custom project is already part of the editor.**

You'll also need a working installation of Microsoft's Visual Studio in order for the editor to be able to compile the project.

- Dragon Ball FighterZ requires Visual Studio 2017.
- Guilty Gear -Strive- is already compiled, so you do not need Visual Studio.
- DNF Duel, and Granblue Fantasy Versus Rising require Visual Studio 2019.

For more information on how to set up Visual Studio for UE4, [read the official Unreal Engine documentation](https://docs.unrealengine.com/4.26/en-US/ProductionPipelines/DevelopmentSetup/VisualStudioSetup/).
