# Getting the project for your game

<hr>

The prebuilt custom projects provide all of the custom asset types the game supports, and for newer games, they even include many assets from the game, such as UI elements or data tables. 

Below are download links for each game:

- [Dragon Ball FighterZ custom project](https://drive.google.com/file/d/1-wjbe0aE4Xs8S7AunSB0XtAE-sSZsOnW/view?usp=sharing)
- The original Granblue Fantasy Versus does not have a custom project.
- Guilty Gear -Strive-'s custom project is bundled with the editor.
- [DNF Duel custom project](https://1drv.ms/u/s!ApT7KvOr_B0hgY3rUBgqs787KHi5_iY?e=xKuxrI)
- [Granblue Fantasy Versus Rising custom project](https://drive.google.com/file/d/1aA1WYxkxpOUpNqSi5kANLUhh4Ja7A_4l/view?usp=drive_link)



<details><summary>Guilty Gear-specific information</summary>
<br>

The Guilty Gear -Strive- custom project does not come with content by default. To get the content, you can copy `pakchunk0-WindowsNoEditor.pak` from your copy of Strive into `RED\Content\Paks`. If the Paks folder does not exist, create it. 

Alternatively, you can create a [symbolic link](https://www.howtogeek.com/16226/complete-guide-to-symbolic-links-symlinks-on-windows-or-linux/) in Windows by either using one of the tools on the linked page or opening a Command Prompt in the `RED/Content/Paks` directory and using a command like this: 
<br>
`mklink pakchunk0-WindowsNoEditor.pak "C:\Program Files (x86)\Steam\steamapps\common\GUILTY GEAR STRIVE\RED\Content\Paks\pakchunk0-WindowsNoEditor.pak"`. 

This saves around 30 GB of hard drive space, since you're not duplicating the files in two places - and it will also update automatically.
If this doesn't work, run as administrator - I also wasn't able to do this in Powershell, *only* Command Prompt.

Additionally, the Strive project may receive asset patches for certain assets. To use these, extract `GGSTContent_Patch.rar` into `RED`.

Finally, if you don't want to do active work in the Advanced Project (due to the quantity of files), you can create a new project under the File dropdown at the top left - however, i've found **this has to be "christened"** by copying the `Config` folder from `/RED/` into your new project's folder, overwriting as necessary. If this step is not done, cooking won't work.

<hr>
</details>

Once you have downloaded the correct project, extract it to your Unreal Projects directory. If you've run the editor before, you can usually find it at `Documents\Unreal Projects\`. **For Guilty Gear -Strive-, the custom project is already part of the editor.**

You'll also need a working installation of Microsoft's Visual Studio in order for the editor to be able to compile the project.

- Dragon Ball FighterZ requires Visual Studio 2017.
- Guilty Gear -Strive- is already compiled, so you do not need Visual Studio.
- DNF Duel, and Granblue Fantasy Versus Rising require Visual Studio 2019.

For more information on how to set up Visual Studio for UE4, [read the official Unreal Engine documentation](https://docs.unrealengine.com/4.26/en-US/ProductionPipelines/DevelopmentSetup/VisualStudioSetup/).
