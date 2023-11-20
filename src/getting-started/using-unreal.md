# How to use Unreal Engine

After downloading the custom Unreal Engine build, you may be wondering how to use it. If you are on version 23H2 of Windows 11, the operating system will be able to decompress the archive file itself. Simply right-click the file and click Extract All from the context menu.

If you are on an older version of Windows, you will need third-party software like [WinRAR](https://www.win-rar.com/) to extract the file. A guide for extracting files with WinRAR can be found [here](https://www.win-rar.com/open-rar-file.html?&L=0).

The extraction process will take a while, especially depending on your hardware. For best results, you should use a solid state drive to store your Unreal Engine build.

Once that is complete, open the folder in File Explorer, and navigate to Engine\Binaries\Win64. Find the UE4Editor executable and run it. When running it for the first time, it will take a while to compile shaders. If you're unsure why Unreal is taking so long to open, open Task Manager and check the process for high CPU usage, or look for ShaderCompileWorker processes within it. These two are proof of compiling shaders.

Once Unreal finishes initializing, you will be met with the Project Browser menu. While you could create your own project from scratch, this is not recommended. Arc System Works uses many custom asset types that require custom prebuilt projects to use. The next page will go into more detail.