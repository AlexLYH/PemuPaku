# PemukulPaku

## Getting Started
[GitHub wiki](https://github.com/rafi1212122/PemukulPaku/wiki)

## Development
[Building](https://github.com/rafi1212122/PemukulPaku/wiki/Development#building)

## Support
[Discord server](https://discord.gg/fbsRYc7bBA) or GitHub issue

A guide for installing and using PemukulPaku.

PemukulPaku is a Hi3 private server written with C#, made by @rfi.
It still has some bugs at the time of writing but is easy enough to use.

Note that this guide is made for version 6.8.0 GLB and SEA. If you try to run a version other than 6.8.0. (or if you want to run the CN version of 6.8.0.) there is no guarantee it will work, and you may have to find crucial cache/game files yourself.
This guide does not include downloads for the HD cutscenes or audio as I have yet to find them.

Prerequisites
- Reading comprehension
- .NET 6.0 SDK (https://dotnet.microsoft.com/en-us/download/dotnet/6.0)
- MongoDB (https://www.mongodb.com/try/download/community)
- Either Mitmproxy (https://mitmproxy.org/) or Fiddler Classic (https://www.telerik.com/fiddler/fiddler-classic)

Deciding between using Mitmproxy or Fiddler Classic is up to you, but if you are unfamiliar with them I recommend Mitmproxy as it is the one I will be using in this guide.

Hi3 6.8.0. GLB can be downloaded from https://drive.google.com/file/d/1ypsWJIdvxx1cQJQuKmpH-FOvdJ7-N3cE/view?usp=sharing and Hi3 6.8.0. SEA can be downloaded from https://drive.google.com/file/d/1gCw7exthn5pFddFv-zWLFpSFE7c1qNdE/view?usp=sharing

Other important files (such cache files, the proxy.py used by Mitmproxy, and--of course--PemukulPaku itself) can be found at https://drive.google.com/drive/folders/1HKWJr_10ttA30acPnxuCd8hPhOQldxJt?usp=drive_link

After extracting all of the files, the folder structure should look something like this:

├── Hi3 app folder
│ ├── AntiCheatExpert
│ ├── BH3_Data
│ ├── net6.0 (Contains the PemukulPaku app)
│ ├── cache (You must make this folder yourself, then extract the Data and Resources folders from the provided cache zip file here)
│ ├── proxy.py
│ ├── BH3Base.dll
│ ├── bugtrace.dll
│ ├── pkg_version
│ ├── UnityPlayer.dll
│ └── BH3.exe

There will be some other files in there after the first launch, and the files and folders might not be in this exact order.

Before opening PemukulPaku for the first time, you need to run these commands in Powershell or command prompt
dotnet dev-certs https
dotnet dev-certs https --trust

To use PemukulPaku:
- Run these commands in Powershell or command prompt:
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyServer /t REG_SZ /d "127.0.0.1:8080" /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyEnable /t REG_DWORD /d 0x1 /f

Note that running these commands will temporarily cut your internet connection.

- open PemukulPaku.exe
- use the cd command to go to the directory proxy.py and BH3.exe are in (for example, cd C:\Program Files\Honkai Impact 3\Games)
- run the command mitmdump -k -s .\proxy.py
- open BH3.exe and do whatever you'd like

After you are done playing:
- close BH3.exe
- close Pemukulpaku.exe
- close the mitmdump proxy.py proxy
- run this command to regain internet access:
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyEnable /t REG_DWORD /d 0x0 /f

Alternatively, you can use these scripts, just be sure to change the paths as needed https://drive.google.com/drive/folders/1Wseikd6eB5HsUtKVcfU1UCE30fy8iPoo?usp=drive_link

If something goes wrong or does not work, the lovely people of this Discord will probably help you.
