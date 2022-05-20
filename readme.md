**0. What is this?**

This is the instruction to make your Windows Terminal look cool.  

There is a lot of articles online on this topic already. However, I couldn't find anything that covers how to set up: 

1. `Windows PowerShell`
2. `Git Bash` 
3. `CMD Command Line` 
4. `VS Code Terminal`
   
All in one place. So, I have decided to put all my findings together and make it convenient those who need it. 

Screenshot to show that it works with `PowerShell`, `git bash` and `cmd`:
![demo](./images/demo.png "demo")
Screenshot to show that it works on `VS Code` as well:
![demo](./images/demo2.png "demo")

So are you ready?

--------------------------------------------
**1. Windows Terminal 7**

Download and install Windows Terminal if you don't have it.

Create a Terminal shortcut with escalated Administrator rights.

Firstly, on your desktop, right click to bring up the menu and choose `create shortcut`

Properties->Shortcut tab->Target as:

`%LocalAppData%\Microsoft\WindowsApps\wt.exe`

Properties->Shortcut tab->Start in:

`%userprofile%\AppData\Local\Microsoft\WindowsApps`

Properties->Shortcut tab->Change Icon:

find .ico in `\images` assets and copy it to your folder below:

`%userprofile%\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\terminal.ico`
(WindowsTerminal_{appid} may vary according to your computer)

Properties->Shortcut tab->Advanced:

check `'Run as Administrator'`

Right-click the shortcut on your desktop and choose `'Pin it to taskbar'`

Now, run the Windows Terminal shortcut and see it work.

Open Windows Terminal settings by clicking the gear button from the drop-down menu, then click the left bottom gear button to open your `settings.json` file.

Copy & paste this code into it:

(Replace my `defaultProfile` and `guid`s with yours in your settings file)

    {
        "$help": "https://aka.ms/terminal-documentation",
        "$schema": "https://aka.ms/terminal-profiles-schema",
        "actions": [],
        "defaultProfile": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
        "profiles": 
        {
            "defaults": 
            {
                "background": "#223344",
                "backgroundImage": "ms-appdata:///local/lime-os-M.png",
                "backgroundImageAlignment": "topRight",
                "backgroundImageStretchMode": "none",
                "colorScheme": "Lime",
                "cursorColor": "#FFFFFF",
                "cursorShape": "bar",
                "experimental.retroTerminalEffect": false,
                "font": 
                {
                    "face": "3270Medium Nerd Font",
                    //"face": "CodeNewRoman Nerd Font",
                    "size": 10
                },
                "hidden": false,
                "historySize": 9001,
                "opacity": 95,
                "padding": "0, 0, 0, 0",
                "snapOnInput": true,
                "startingDirectory": "%USERPROFILE%",
                "useAcrylic": false
            },
            "list": 
            [
                {
                    "closeOnExit": "graceful",
                    "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
                    "icon": "ms-appx:///ProfileIcons/{0caa0dad-35be-5f56-a8ff-afceeeaa6101}.png",
                    "name": "cmd",
                    "tabTitle": "cmd"
                },
                {
                    "closeOnExit": "graceful",
                    "commandline": "\"%PROGRAMFILES%\\git\\usr\\bin\\bash.exe\" -i -l",
                    "guid": "{78b4b215-5722-447b-8b7e-093f96493df2}",
                    "icon": "%LOCALAPPDATA%/Packages/Microsoft.WindowsTerminal_8wekyb3d8bbwe/LocalState/git-bash.png",
                    "name": "Git Bash",
                    "tabTitle": "Bash"
                },
                {
                    "closeOnExit": "graceful",
                    "guid": "{574e775e-4f2a-5b96-ac1e-a2962a402336}",
                    "icon": "ms-appx:///ProfileIcons/{574e775e-4f2a-5b96-ac1e-a2962a402336}.png",
                    "name": "Windows PowerShell",
                    "source": "Windows.Terminal.PowershellCore",
                    "tabTitle": "PowerShell"
                },
                {
                    "closeOnExit": "never",
                    "commandline": "Azure",
                    "connectionType": "{d9fcfdfa-a479-412c-83b7-c5640e61cd62}",
                    "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
                    "icon": "ms-appx:///ProfileIcons/{b453ae62-4e3d-5e58-b989-0a998ec441b8}.png",
                    "name": "Azure Cloud Shell",
                    "source": "Windows.Terminal.Azure"
                }
            ]
        },
        "schemes": 
        [
            {
                "name": "Lime",
                "foreground": "#E8F4FF",
                "background": "#1A1A1A",
                "cursorColor": "#FFFFFF",
                "selectionBackground": "#FFFFFF",
                "black": "#000000",
                "blue": "#579BD5",
                "cyan": "#00B6D6",
                "green": "#4EC9B0",
                "purple": "#714896",
                "red": "#E92888",
                "white": "#EAEAEA",
                "yellow": "#CE9178",
                "brightBlack": "#797979",
                "brightBlue": "#9CDCFE",
                "brightCyan": "#2BC4E2",
                "brightGreen": "#1AD69C",
                "brightPurple": "#975EAB",
                "brightRed": "#EB2A88",
                "brightWhite": "#EAEAEA",
                "brightYellow": "#E9AD95"
            }
        ],
        //experimental feature, prefer to disable it. 
        "useAcrylicInTabRow": false 
    }
 
--------------------------------------------
**2. Fonts**

I have chosen these 2 fonts to work with, let's install them:

https://www.nerdfonts.com/font-downloads

Download and install `3270 font` (for Windows Terminal)

Download and install `MesloLGM Nerd Font` (for Visual Studio Terminal)

--------------------------------------------
**3. Background image**

Put the png and ico files into the same folder as the `setttings.json` in:

`%userprofile%\AppData\Local\Packages\Microsoft.WindowsTerminal_{appid}\LocalState`

You can get my half transparent logo or use your own picture.
Note that you may want to adjust the picture positioning in:

`settings.json` -> `backgroundImageAlignment`.


---------------------------------------
**4. PowerShell**

Download the latest powerShell and install it from https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows

#Terminal-Icons: displays colour folder & file icons. 

#PSReadLine: gives you intellisense when you type. They are available in PowerShell only, not cmd or git bash.

to install in powerShell type:

`Install-Module -Name Terminal-Icons`
Press A or Y

`Install-Module -Name PSReadLine`
Press A or Y

--------------------------------------------
**5. oh-my-posh**

Take a loot at `oh-my-posh` from https://ohmyposh.dev/docs/installation/windows and see what it is. 

open PowerShell to install it by typing:

`winget install oh-my-posh`

Make sure your Windows environment variable is pointing to:

`Path -> C:\Users\kelvi\AppData\Local\Programs\oh-my-posh\bin`

Restart PowerShell and check that it is working by typing: 

`oh-my-posh` 

(You may need to restart the terminal, or restart the pc for it to take effect)

Now in PowerShell test the profile .sp1 file location by typing:

`echo $PROFILE`  

Create the file if does not exist `/Documents/PowerShell/Microsoft.PowerShell_profile.ps1`  and write this into the file:

    oh-my-posh init pwsh --config ~/.jandedobbeleer.omp.json | Invoke-Expression
    Import-Module -Name Terminal-Icons 
    Import-Module -Name PSReadLine 
    Set-PSReadLineOption -PredictionSource History
    Set-PSReadLineOption -PredictionViewStyle ListView
    Set-PSReadLineOption -EditMode Windows

Restart Windows Terminal to see it take effect.

----------------------------------------
**6. Configure Git Bash & VS Code**

First, you can update git in cmd:

`git update-git-for-windows`

turn on git bash and check:

`oh-my-posh` (to see it actually working)

`echo $HOME` (it should be the same as your cmd & powershell home directory) 

Go to the home directory `C:/Users/{your_name}/` then edit or create the `.bashrc` file:
    
    eval "$(oh-my-posh --init --shell bash --config ~/.jandedobbeleer.omp.json)"

Restart Windows Terminal to see it take effect.

Now, once the git bash works, your VS Code integrated terminal should also be working.
You can open VS code terminal to test it.

As mentioned above, a Nerd Font is needed for VS Code if you have not already done it. 

Go to VS Code, settings search for `terminal.integrated.fontFamily` and set the font and size there. I have chosen:

`MesloLGM Nerd Font` and `size 10`.

(If you have newly installed the font make sure you restart VS to take effect)

----------------------------------------
**7. Configure cmd**

Get `Lua` from http://luabinaries.sourceforge.net/download.html

No need to install it, just extra all files to the following folder and add Windows system variables:

`path -> add c:/Program Files/lua`

(Make sure system variables works by typing lua54.exe in a terminal, you may need to restart the cmd, or restart the pc)

Also get `Clink` from https://github.com/chrisant996/clink/releases

Once you have installed it, you will go to the following folder:

`%userprofile%\AppData\Local\clink`

Create `cmd-oh-my-posh.lua` file in the folder:

    local custom_prompt = clink.promptfilter(50)
    function custom_prompt:filter(prompt)
        load(io.popen('oh-my-posh init cmd --config ~/.jandedobbeleer.omp.json'):read("*a"))()
    end

Restart Windows Terminal to see it take effect.
-----------------------------------------
**8. For WSL**

To be explored, but it should be pretty standard following the oh-my-posh docs.

-----------------------------------------
**9. Related Software & Versions**

| Software         | Version               |
|------------------|-----------------------|
| Windows Terminal | [ v1.12.10983.0 ]     |
| PowerShell       | [ v7.2.4 win x64 ]    |
| git              | [ v2.36.1.windows.1 ] |
| clink            | [ v1.3.17.0a95d0 ]    |
| lua              | [ v5.4.2 ]            |

-----------------------------------------
**10. Known Issues**

#1. I noticed that the text & icons in `oh-my-gosh` path is not align properly with my theme.

![issue1](./images/issue1.png "issue")

#2. The profile takes 2~3 seconds to load up.

![issue2](./images/issue2.png "issue")