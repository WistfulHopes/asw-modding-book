# Starting the editor

<hr>

Extract all of the contents from the custom UE4 archive you downloaded in the previous step. You can use tools like [WinRAR](https://www.win-rar.com/) or [7-Zip](https://www.7-zip.org) to do so.

Once that is complete, you can fire up the engine with `.\Engine\Binaries\Win64\UE4Editor.exe`

The current Guilty Gear -Strive- editor works differently. It will be booted from `.\RED\Binaries\Win64\GGSTCookedEditor.exe`. 

**You do not need the Epic Games Launcher for this.**

<br />

The first boot of the UE4 editor usually takes a while to get going. If you want to check whether it's actually starting or not, open Task Manager (Ctrl + Shift + Esc) and check for high CPU usage. This usually means it's busy compiling shaders.

Once Unreal finishes initializing, you will be met with the Project Browser menu. While you could create your own project from scratch, we highly recommend starting off with one of the [pre-made custom projects.](custom-project.md)