## LiveSplit.IGTReaderHotKey
A simple hotkey that reads out the current IGT, mainly used for ALT + Space Force Quitout WrongWarps in Blindfolded Dark Souls 1 Speedruns.
To activate it, add the built component in the LiveSplit "Component" folder, and then add it as a Layout in the "Media" section.
**IMPORTANT: This component is currently based on the "Counter" plugin, and will be treated as an extension to that for now. This might change in the future when I decide to clean this up.**

## Compiling / Setup
To change the code and built it yourself, you first need to clone and built the LiveSplit repository over at https://github.com/LiveSplit .
Some useful information for that:
LiveSplit is written in C# 7 with Visual Studio and uses .NET Framework 4.6.1. To compile LiveSplit, you need one of these versions of Visual Studio:
 - Visual Studio 2017 Community Edition
 - Visual Studio 2017

Simply open the project with Visual Studio and it should be able to compile and run without any further configuration.

Sometimes, you will get a compilation error though. Common errors are listed here:
1. Could not build Codaxy.Xlio due to sgen.exe not being found. Open LiveSplit\\Libs\\xlio\\Source\\Codaxy.Xlio\\Codaxy.Xlio.csproj in order to edit where it looks for this path. Look for <SGen...> where it defines the attribute "ToolPath". Look on your computer to find the proper path. It is typically down some path such as "C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\x.xA...". Find the version you want to use and bin folder with sgen.exe in it and replace the path in the .csproj file.
2. No submodules pulled in when you fork/clone the repo which causes the project not to build. There are two ways to remedy this:
 - Cloning for the first time: `git clone --recursive git://repo/repo.git`
 - If already cloned, execute this in the root directory: `git submodule update --init --recursive`
 
 After building the LiveSplit repository in Visual Studio 2017, you can add the LiveSplit.Speech project file (from the source code) as a subproject into the LiveSplit project structure. It should be put into Components/Media/ . From there on, you can change the source code and finally built the LiveSplit.Speech component itself. The output path for the .dll should be displayed in the console.
 
 Important: You might need to change the current .NET version of the project in properties -> .Net Framework Version.

# Packages / Requirements (copied from Counter)

- If you plan on building this solution yourself, you may need to add references to the following dlls (the included versions may be outdated), all of which are distributed with LiveSplit: [http://livesplit.org/](http://livesplit.org/ "Livesplit Home").
	+ LiveSplit.Core.dll
	+ UpdateManger.dll
	+ WinformsColor.dll
 
 
