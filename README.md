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




guide for installing/using PemukulPaku.

PemukulPaku is a Hi3 private server written with C#, made by rafi1212122 and contributors (sinsofseven,kyle873, and others in github https://github.com/Sycamore0/PemukulPaku/graphs/contributors)
Its not in complete state, but yea, its better than nothing. 
Sadly the original github page hitted by a DMCA strike, but there is a lot of people forking it.. 
sadly theres not a lot of people maintain the project anymore soo its a inclompete abandonware app for now
(i hope there someone revive this project tbh :/)

I written this guide because when I want to install pemukulpaku, i need to scour the intire server for the app, files, like that for instalation data and guides 
so i gather all the links and put it here and wanted contibute this project but i not really an coding expert 
btw, not for resale, this project is open source :shrug:

Discord sever, maybe for help, or contribute
https://discord.gg/fbsRYc7bBA

Original github repo
https://github.com/Sycamore0/PemukulPaku
https://web.archive.org/web/20230616045426/https://github.com/rafi1212122/PemukulPaku (archived version)

one of the fork archive of the github repo
https://github.com/Sycamore0/PemukulPaku

Wiki (Archived)
https://web.archive.org/web/20230616045426/https://github.com/rafi1212122/PemukulPaku/wiki

HI3 app, you need and active Hi3 version because the launch chache\resource chache shenanigan (SEA,GLB,TWHKMO,JP 6,8) (CN 6.9)
## for me tested on GLB 6.8 works for me with cache patch, SEA works but no cache patch yet, CN maybe.. havent tested but there is the patch, other IDK, maybe scour this server tbh im lazy :/
## if the game official server is updated like to 6.9 maybe previous version or older like 6.8 not works except you have the launch/resource cache..
## 6.9 SEA/GLB/TWHKMO/JP Patch is 1 week left tbh

6.8
SEA https://hk-bigfile-os-mihayo.akamaized.net/ptpublic/bh3_overseas/20230731130650_CvWDc5ChckYsPWZ1/BH3_v6.8.0_a257d1d8849b.7z
GLB https://hk-bundle-west-mihayo.akamaized.net/ptpublic/bh3_global/20230731131247_XJqyuS1Y9BN12Ts8/BH3_v6.8.0_a257d1d8849b.7z

6.9 CN
https://bundle.bh3.com/ptpublic/rel/20230814114102_KD8RjBDLGc0wU5j9/PC/BH3_v6.9.0_d09f54ae2822.7z

This is maybe clone of the github repo..

Prerequisites
- Reading comprehension
- GitHub account
- .NET 6 SDK (https://dotnet.microsoft.com/en-us/download/dotnet/6.0)
- MongoDB (https://www.mongodb.com/try/download/community)

for proxy you can use Fiddler or Mitmproxy, but im used mitmproxy, haven't used fiddler
- mitmproxy (https://mitmproxy.org/)
- Fiddler Classic (https://www.telerik.com/fiddler/fiddler-classic)


If you want to build and compile from scratch (Development Building)

Before Building
Download and put resources in Common\Resources
├───Common
│   └───Resources
│       └───ExcelOutputAsset
│       └───Proto.cs

Building
Use Dotnet CLI after installing .NET 6 SDK, or build using Visual Studio(recommended)
https://learn.microsoft.com/en-us/dotnet/core/tools/
dotnet build --output ./build_output

Offline Patch (GLB server) thanks eqogkb (https://discord.com/channels/1109243478325596250/1115067916342276146/1137096779180027914)
for anyone interested in playing on older versions/playing fully offline (only works for global, but easily modifiable for other regions):
apply this patch to PemukulPaku
https://cdn.discordapp.com/attachments/1115067916342276146/1137245092957134848/offline.patch
in config.json set Host to 127.0.0.1
and use this mitmproxy script
https://cdn.discordapp.com/attachments/1115067916342276146/1137264001429028885/proxy.py
the first time you start the game it will cache the response of the update server in the cache folder
and on subsequent runs it will return the cached file

Offline Patch (CN server) (#the patch script is from eqogkb, but modified to use on CN server, haven't tested it myself) thanks Munplad#2194 (https://discord.com/channels/1109243478325596250/1115972937565081692/1137947847178854400)
for cn version patch,you no longer need to download exceed 4000MB updates when switching back to the official server.
it work on windows,i'm not sure if this py script will work completely, but it work in the test.
.patch file https://cdn.discordapp.com/attachments/1115972937565081692/1137947846482612334/offline.patch
proxy file https://cdn.discordapp.com/attachments/1115972937565081692/1137947846872678431/proxy.py

Compiled version with the GLB server Offline patch, if you doesnt want to compile but idk thanks _michaelwhite
https://drive.google.com/file/d/1-p8b-KZwzJGG8zt3asjr0eP8iO9iJrly/view?usp=sharing

This is from the old guide, maybe it helps
- pemukulpaku app        https://www.mediafire.com/file/iotu6it6hhij1cs (no offline patch)
- resources.zip        https://www.mediafire.com/file/xf8wux739lry7po
- proto            https://rafi12.cyou/files/Proto.zip
- 6.7 ExcelAsset partial Patch    https://cdn.discordapp.com/attachments/1109243665156685854/1124199030604431470/6.7_ExcelAsset_Partial_Patch.zip
- proxy            https://gist.githubusercontent.com/rafi1212122/5cc76297d6cf6396de5fc572d1e55812/raw/ea7075c2f370256faf570e79b76aa730c6ac24f6/proxy.py (before offline patch)

after downloading and install the application dependencies unzip the the app, resources, proto, 6.7 patch, and proxy and put the files like this

├── Hi3 app folder 
│   ├── net6.0 (this the pemukulpaku app) (extract resources.zip here)
│   │    ├── resoruces (and put the 6.7 ExcelAsset patch inside the resources folder here for 6.7 characters if you use 6.7)
│   │    └── proto.cs (put the proto here)
│   └── proxy.py

before opening pemukulpaku, you need run this commands in powershell
dotnet dev-certs https
dotnet dev-certs https --trust

for starting the ps
- you need to run these commands :
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyServer /t REG_SZ /d "127.0.0.1:8080" /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyEnable /t REG_DWORD /d 0x1 /f
- open pemukulpaku.exe app
- run these commands in the Hi3 app folder directory
mitmdump -k -s .\proxy.py
- open bh3.exe app and enjoy

after using the server and close the game do this
- close Pemukulpaku
.exe
- close the mitmdump proxy.py proxy
- run this command :
reg add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyEnable /t REG_DWORD /d 0x0 /f

common errors
https://discord.com/channels/1109243478325596250/1109243665156685854/1116226589508771860
https://media.discordapp.net/attachments/1109243479814570008/1125088634731769856/2.jpg?width=853&height=535

GM Commands
https://media.discordapp.net/attachments/1109243479814570008/1125088634996019320/3.jpg?width=853&height=535

ids valk (6.6)
https://discord.com/channels/1109243478325596250/1109243665156685854/1123596404556824638

weap ids and stats
https://discord.com/channels/1109243478325596250/1109243479814570008/1109855877504184412

valk,stig,weap,outfit (6.7)
https://discord.com/channels/1109243478325596250/1109243665156685854/1124100152102232246
