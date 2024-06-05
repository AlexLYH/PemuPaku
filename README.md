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



al
alalal_
Idle
client tls handshake failed
Xodd4869 — 08/19/2023 10:48 PM
in-game error
and what does that report one says
Evie <3 — 08/19/2023 10:48 PM
what?
Xodd4869 — 08/19/2023 10:49 PM
Image
double click and show what it says
Evie <3 — 08/19/2023 10:49 PM
Image
image.png
107.09 KB
725x487px
Xodd4869 — 08/19/2023 10:50 PM
raw
or webview
Evie <3 — 08/19/2023 10:51 PM
for response or request headers
Xodd4869 — 08/19/2023 10:51 PM
res
Evie <3 — 08/19/2023 10:51 PM
Image
image.png
27.01 KB
708x484px
Xodd4869 — 08/19/2023 10:52 PM
wait meant request
Evie <3 — 08/19/2023 10:52 PM
GET /report?logType=login_log&channelID=v6.8.0_global_pc&asb=1385247&event=ConnectGlobalDispatch&result=SUCC&retDesc=&regionName=overseas01&deviceID=cac311f62f3c24f646c22834abde57b22d834ee6&sessionID=1692452882&guessUID=105361189&reportTime=1692452899471&operatingSystem=Windows+11++(11.0.0)+64bit&deviceModel=82K1+(LENOVO)&identifier=-1342613688&uaPc=&extMsg= HTTP/1.1
Host: localhost
User-Agent: UnityPlayer/2017.4.18f1 (UnityWebRequest/1.0, libcurl/7.51.0-DEV)
Accept: /
Accept-Encoding: identity
X-Unity-Version: 2017.4.18f1
Xodd4869 — 08/19/2023 10:54 PM
what does in-game error shows
Evie <3 — 08/19/2023 10:56 PM
Image
Honkai_Impact_3rd_8_19_2023_9_54_53_AM.png
1.45 MB
1920x1080px
Xodd4869 — 08/19/2023 10:56 PM
LocalLow\miHoYo\Honkai Impact 3rd
and check output_log there does it have any error
try reinstalling fiddler certificate ig
is your server running? 
Evie <3 — 08/19/2023 10:57 PM
Image
image.png
83.69 KB
1094x631px
Xodd4869 — 08/19/2023 10:58 PM
dont select it
that legit pauses it
this server need more logs
Evie <3 — 08/19/2023 10:59 PM
should i restart it
and does it matter which i start first between fiddler and the server?
Isaac Newton (B) — 08/19/2023 11:01 PM
Modder helping now that the PS is broken?
Xodd4869 — 08/19/2023 11:03 PM
i always find myself helping
pain bad habbit
Isaac Newton (B) — 08/19/2023 11:03 PM
No as long as both are running when you start the game
Xodd4869 — 08/19/2023 11:03 PM
and ts version worked so this one should work
Isaac Newton (B) — 08/19/2023 11:04 PM
Something something login API requires an update
Something something need to add something about free TW to the cli
Evie <3 — 08/19/2023 11:05 PM
now im even more confused
Isaac Newton (B) — 08/19/2023 11:05 PM
Nothing I said applied to you except the reply 
Evie <3 — 08/19/2023 11:05 PM
I figured, but im still confused
thats just who i am as a person
Tuấn Anh — 08/19/2023 11:49 PM
@Evie <3 you should use mitmproxy instead of fiddler, i have tried fiddler and get the same error :V switching to mitmproxy and it worked
and use the cmd line in the installation guide in this server too
Iwillturntheworld — 08/19/2023 11:54 PM
How to make cn6.9 work?change what src
Tuấn Anh — 08/19/2023 11:54 PM
work for what?
Iwillturntheworld — 08/19/2023 11:55 PM
this
Tuấn Anh — 08/19/2023 11:56 PM
like I said above :V you can try them tho ⁠support⁠ 
but if it's the socket error, you have to find out the beginning socket cause that error ( or reset your pc is the fastest way =))) ) 
Tuấn Anh — 08/20/2023 12:08 AM
just open your game folder which already have proxy.py and type the cmd in the guide
Evie <3 — 08/20/2023 12:09 AM
do i need to open mitmproxy itself
Iwillturntheworld — 08/20/2023 12:09 AM
Image
image.png
111.11 KB
833x519px
Image
image.png
904.97 KB
1680x1050px
Xodd4869 — 08/20/2023 12:11 AM
u dont
Evie <3 — 08/20/2023 12:12 AM
alright, here we go
fingers crossed
same thing
connection error. please try again later
Xodd4869 — 08/20/2023 12:14 AM
what did mitm show
how does your windows proxy settings look like
did u close fiddler
Evie <3 — 08/20/2023 12:15 AM
i closed fiddler, opened pempalu, ran the mitmdump -k -s .\proxy.py thing in C:\Program Files\Honkai Impact 3rd glb\Games, and i started the game
Isaac Newton (B) — 08/20/2023 12:16 AM
So you didn't enable windows proxy
rfi — 08/20/2023 12:16 AM
set the mitm ports manually in settings 
Image
image.png
58.13 KB
894x630px
Xodd4869 — 08/20/2023 12:16 AM
hit save few times
till mitm window print
cuz windows is dumb
Evie <3 — 08/20/2023 12:16 AM
its on
Image
image.png
26.9 KB
658x578px
rfi — 08/20/2023 12:17 AM
save and you'll see output in mitm if u use internet
Isaac Newton (B) — 08/20/2023 12:17 AM
If it's on, and you can still use discord, it's working
Xodd4869 — 08/20/2023 12:18 AM
still didnt send the log i asked for
Evie <3 — 08/20/2023 12:18 AM
im working on it
Xodd4869 — 08/20/2023 12:20 AM
make it server for eva version
Image
Evie <3 — 08/20/2023 12:20 AM
you're gonna have to explain it to me as if you're talking to a senior citizen
Xodd4869 — 08/20/2023 12:21 AM
Image
Tuấn Anh — 08/20/2023 12:23 AM
nope, through the terminal/powershell/cmd
Xodd4869 — 08/20/2023 12:23 AM
still didnt show mitm window
Evie <3 — 08/20/2023 12:24 AM
im working on it
Image
image.png
183.58 KB
1442x835px
Xodd4869 — 08/20/2023 12:25 AM
reopen game
Evie <3 — 08/20/2023 12:27 AM
how about i just go to general and screen present what's happening
Image
image.png
235.38 KB
1887x962px
Xodd4869 — 08/20/2023 1:07 AM
Image
Evie <3 — 08/20/2023 1:30 AM
Look, i tried to understand and i get that its frustrating but i just dont get it
Xodd4869 — 08/20/2023 1:31 AM
sometimes it just doesnt work
Evie <3 — 08/20/2023 1:31 AM
right, but there's always a reason
Xodd4869 — 08/20/2023 1:31 AM
so true
send me the log
Evie <3 — 08/20/2023 1:31 AM
can you just walk me thru step-by-step how to set it up and ill just start over
Xodd4869 — 08/20/2023 1:32 AM
told u i never used this version so idk about step by step
Isaac Newton (B) — 08/20/2023 1:33 AM
@Evie <3From what I've seen you set it up properly tbh.
Show what your pemu looks like when you try to connect
Evie <3 — 08/20/2023 1:33 AM
ok one sec
im finishing sum rq
Isaac Newton (B) — 08/20/2023 1:34 AM
Image
everything past here means that the game is connecting
Image
image.png
198.71 KB
838x353px
Xodd4869 — 08/20/2023 1:35 AM
this why im asking for game log
Evie <3 — 08/20/2023 1:35 AM
ok, to make sure, wdym game log? i have an idea but I want to make sure
Isaac Newton (B) — 08/20/2023 1:36 AM
There is a small chance that the pemu config.json is bricked 
But since you're having so much trouble it seems more likely
Evie <3 — 08/20/2023 1:37 AM
Image
image.png
18.97 KB
1806x870px
Isaac Newton (B) — 08/20/2023 1:37 AM
that doesn't look right
you shouldn't be connecting to an IP that ends in .1, that's a gateway IP
you can just delete the file
Evie <3 — 08/20/2023 1:38 AM
thats how it was when i downloaded it, so idk what to do about it
Isaac Newton (B) — 08/20/2023 1:39 AM
just delete it and restart the server
and I mean delete the file
the server will generate a new one
Evie <3 — 08/20/2023 1:40 AM
ok so i just did that and its the same one
Xodd4869 — 08/20/2023 1:41 AM
LocalLow\miHoYo\Honkai Impact 3rd\output_log.txt
Isaac Newton (B) — 08/20/2023 1:45 AM
@Evie <3when you're done getting the output_log.txt
in a new terminal, run the command ipconfig.
Evie <3 — 08/20/2023 1:45 AM
Initialize engine version: 2017.4.18f1 (000000000000)
[MHY] miHoYo engine version: 5480
GfxDevice: creating device client; threaded=1
Direct3D:
    Version:  Direct3D 11.0 [level 11.1]
    Renderer: NVIDIA GeForce RTX 3050 Laptop GPU (ID=0x25a2)
Expand
output_log.txt
20 KB
Image
image.png
80.53 KB
1920x963px
Isaac Newton (B) — 08/20/2023 1:46 AM
okay the server is just grabbing the wrong adapter
192.168.86.27
Evie <3 — 08/20/2023 1:46 AM
you want me to put that in config?
Isaac Newton (B) — 08/20/2023 1:46 AM
put this in the config.json
that should just fix it
Evie <3 — 08/20/2023 1:47 AM
alright im trying it out
Isaac Newton (B) — 08/20/2023 1:47 AM
usually the WSLCore adapter is below your main network adapater
Image
image.png
38.73 KB
677x418px
But it is a virtual adapter, so it doesn't work as you would expect
Evie <3 — 08/20/2023 1:49 AM
ok, everything's set up, im opening the game
no luck 😦
Isaac Newton (B) — 08/20/2023 1:52 AM
Did you restart after SAVING the config.json? 
Evie <3 — 08/20/2023 1:52 AM
yeah
Isaac Newton (B) — 08/20/2023 1:53 AM
Okay, was the error the same or different?
Evie <3 — 08/20/2023 1:53 AM
same, connection error, please try again later
Isaac Newton (B) — 08/20/2023 1:53 AM
Are you getting logs in pemu?
Evie <3 — 08/20/2023 1:53 AM
hold on, let me start it again
Image
image.png
88.05 KB
1098x593px
Image
image.png
173.06 KB
1471x735px
are there the 6.8 resources to put in net6.0 
Isaac Newton (B) — 08/20/2023 1:58 AM
that wouldn't fix this
Evie <3 — 08/20/2023 1:58 AM
hmm
could it have to do with this?
Image
image.png
14.6 KB
728x97px
Isaac Newton (B) — 08/20/2023 2:02 AM
don't think so
Evie <3 — 08/20/2023 2:03 AM
should i just delete everything and start over?
Isaac Newton (B) — 08/20/2023 2:03 AM
sometimes that is a valid troubleshooting option, but I don't think it will be effective here.
Evie <3 — 08/20/2023 2:06 AM
well, does the server work for you?
Image
image.png
90.07 KB
969x467px
Image
image.png
113.95 KB
923x113px
OMG THAT MIGHT BE WHY
ITS STILL CONNECTING TO THE OLD THINGY THAT WE CHANGED IN THE CONFIG
Evie <3 — 08/20/2023 2:15 AM
nope
Isaac Newton (B) — 08/20/2023 2:17 AM
Mitmproxy is supposed to connect to localhost (127.0.0.1) 
Evie <3 — 08/20/2023 2:18 AM
i changed it back to the original
so, what might be the problem?
Isaac Newton (B) — 08/20/2023 2:21 AM
@Evie <3 did you ever create a certificate?
dotnet dev-certs https --trust
Evie <3 — 08/20/2023 2:22 AM
yeah
Isaac Newton (B) — 08/20/2023 2:23 AM
I don't really know what's wrong then. You're connecting, at least partially.
And we should have fixed the wrong dispatch IP issue with the config.json
Did you have mongodb setup?
Evie <3 — 08/20/2023 2:25 AM
yes, but let me check on it
OMG ITS WORKING
ok wait
Image
image.png
71.01 KB
1470x318px
cmon why always another issue
i got this one, tho
Xodd4869 — 08/20/2023 2:42 AM
was it cert?
Evie <3 — 08/20/2023 2:49 AM
it works
Xodd4869 — 08/20/2023 2:50 AM
lol
Isaac Newton (B) — 08/20/2023 2:50 AM
I know that at least part of it was the config ip
Xodd4869 — 08/20/2023 2:50 AM
thats last thing i would ever think to check
Isaac Newton (B) — 08/20/2023 2:51 AM
After they changed the config cert they were getting more stuff from pemu
Xodd4869 — 08/20/2023 2:51 AM
told them to reinstall cert so i assumed they did
Isaac Newton (B) — 08/20/2023 2:51 AM
But it still wasn't connecting all the way
So cert, or DB were the last two I said to check
Isaac Newton (B) — 08/20/2023 2:53 AM
Server hosting 101, it's always the IP unless it isn't
Evie <3 — 08/20/2023 2:58 AM
the only question i still have is if there's a way to complete certain story levels using a command
Isaac Newton (B) — 08/20/2023 2:58 AM
No
But there shouldn't be any news for that
Evie <3 — 08/20/2023 2:59 AM
time to grind the story 🤪
Isaac Newton (B) — 08/20/2023 2:59 AM
If you can show me a place where you need it
Like, give me an example
Cause you should be able to do most of the story stages without any issues
Though some of them can freeze your game like the newest chapter
Evie <3 — 08/20/2023 3:00 AM
i think that i need to complete certain story stages to do things like open items n level up valks
Isaac Newton (B) — 08/20/2023 3:00 AM
No lol
You need to be a certain level
You can set your level with commands
Evie <3 — 08/20/2023 3:32 AM
what about augment cores
Isaac Newton (B) — 08/20/2023 5:26 AM
Hahahahaha
MichaeLK955 — 08/23/2023 5:01 AM
Can anyone help me modify my database in HI3 7.0 bata for 6.8 and 6.9 skins and girls and max rank i can pay for your time
Isaac Newton (B) — 08/23/2023 5:11 AM
There isn't even a 7.0 beta, that's literally just 6.9
Xodd4869 — 08/23/2023 5:14 AM
thats why kids shouldnt have money
teikoku — 08/23/2023 12:06 PM
💀
ava_zc — 08/26/2023 12:26 AM
DMCA
unable to download
Ecks — 08/26/2023 12:33 AM
😱
kisakistrike — 08/26/2023 12:34 AM
Yea
There is one, a fork tbh, but you need search deeper 
ava_zc — 08/26/2023 12:36 AM
creperie also
kisakistrike — 09/06/2023 5:05 PM
i'd put it here tbh, v2, idk abt support because im still not 100% understand this PS, ask the contributors of the pemukulpaku project 
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
... (36 lines left)
Collapse
Guide_2.txt
8 KB
疏影. — 09/09/2023 12:47 PM
use offline.patch and proxy,py for glb
Image
Image
got this error
Xodd4869 — 09/09/2023 2:45 PM
sad
kisakistrike — 09/09/2023 7:23 PM
hmm thats weird..
I also still don't understand this patch tbh, can tou screenshot the pemukulpaku and the proxy command prompt?
疏影. — 09/09/2023 7:46 PM
😢
Image
Image
music — 09/09/2023 8:01 PM
How to add seele?
Like
Obtaining the character
kisakistrike — 09/09/2023 8:24 PM
btw do you get the pemukulpaku and compile and patch it yourself ?
maybe use this? its compiled tbh
⁠development⁠
kisakistrike — 09/09/2023 8:28 PM
you need have a 6.8 resource for the PS tbh for adding seele, the most updated i found this server is for 6.7. the ExcelOutputAsset for 6.8 idk god knows is there ExcelOutputAsset resoruce for 6.8 
kisakistrike — 09/09/2023 8:28 PM
there is a GM command in the github wiki, but idk abt for getting a id for seele
﻿
﻿
﻿
﻿
Michael White — 07/16/2023 10:25 PM
and with infinite repeat of "Client TLS handshake failed. The client may not trust the proxy's certificate for gateway.icloud.com (OpenSSL Error([('SSL routines', '', 'inappropriate fallback')]))
[21:24:16.716][192.168.1.7:58382] client disconnect
[21:24:16.966][192.168.1.7:58383] client connect
[21:24:16.994][192.168.1.7:58383] Client TLS handshake failed. The client disconnected during the handshake. If this happens consistently for gateway.icloud.com, this may indicate that the client does not trust the proxy's certificate.
[21:24:16.995][192.168.1.7:58383] client disconnect
[21:24:17.004][192.168.1.7:58384] client connect
[21:24:17.032][192.168.1.7:58384] Client TLS handshake failed. The client disconnected during the handshake. If this happens consistently for gateway.icloud.com, this may indicate that the client does not trust the proxy's certificate.
[21:24:17.032][192.168.1.7:58384] client disconnect
[21:24:17.041][192.168.1.7:58385] client connect"
Michael White — 07/16/2023 10:08 PM
when I open phone HI 3rd "" and each time I click on login client connect
[21:07:37.711][192.168.1.7:52773] client connect
[21:07:37.730][192.168.1.7:52772] Client TLS handshake failed. The client disconnected during the handshake. If this happens consistently for api-account-os.hoyoverse.com, this may indicate that the client does not trust the proxy's certificate.
[21:07:37.730][192.168.1.7:52773] Client TLS handshake failed. The client disconnected during the handshake. If this happens consistently for minor-api-os.hoyoverse.com, this may indicate that the client does not trust the proxy's certificate.
[21:07:37.732][192.168.1.7:52772] client disconnect
[21:07:37.732][192.168.1.7:52773] client disconnect
Client TLS handshake failed. The client disconnected during the handshake. If this happens consistently for log-upload-os.hoyoverse.com, this may indicate that the client does not trust the proxy's certificate.
[21:06:27.644][192.168.1.7:52715] client disconnect
[21:06:27.647][192.168.1.7:52716] Client TLS handshake failed. The client disconnected during the handshake. If this happens consistently for minor-api-os.hoyoverse.com, this may indicate that the client does not trust the proxy's certificate.
[21:06:27.648][192.168.1.7:52716] client disconnect
[21:06:27.967][192.168.1.7:52717] client connect
[21:06:27.969][192.168.1.7:52718] client connect
Expand
message.txt
14 KB
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

