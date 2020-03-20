### windows terminal美化
1. 修改C:\Users\xiongmeng\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\profiles.json
2.
```
// To view the default settings, hold "alt" while clicking on the "Settings" button.
// For documentation on these settings, see: https://aka.ms/terminal-documentation

{
	    "globals" :
    {
        "alwaysShowTabs" : true,
        "copyOnSelect" : false,
        "defaultProfile" : "{0cae0dad-35be-5fc8-abdf-afcedeaa6301}",
        "initialCols" : 120,
        "initialRows" : 30,
        "keybindings" :
        [
        ],
        "requestedTheme" : "system",
        "showTabsInTitlebar" : true,
        "showTerminalTitleInTitlebar" : true,
        "wordDelimiters" : " ./\\()\"'-:,.;<>~!@#$%^&*|+=[]{}~?\u2502"
    },
    "$schema": "https://aka.ms/terminal-profiles-schema",

    "defaultProfile": "{0cae0dad-35be-5fc8-abdf-afcedeaa6301}",

    "profiles":
    {
        "defaults":
        {
            // Put settings here that you want to apply to all profiles
			"fontFace" : "DejaVu Sans Mono", //字体样式
			"fontSize" : 13, //字号
			"foreground" : "#FFFFFF",
			"acrylicOpacity": 1,
   			"useAcrylic": true,
   			"background" : "#012456",
            "closeOnExit" : true,
            "colorScheme" : "UbuntuLegit",
   			"backgroundImage": "C:\\Users\\xiongmeng\\Pictures\\壁纸\\backiee-76116-landscape.jpg",
   			"backgroundImageOpacity": 0.5,
   			"backgroundImageStretchMode": "fill"
        },
        "list":
        [
            {
                // Make changes here to the powershell.exe profile
                "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
                "name": "PowerShell",
                "commandline": "powershell.exe",
                "hidden": false
            },
            {
                // Make changes here to the cmd.exe profile
                "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
                "name": "cmd",
                "commandline": "cmd.exe",
                "hidden": false
            },
            {
                // Make changes here to the cmd.exe profile
                "guid": "{0cae0dad-35be-5fc8-abdf-afcedeaa6301}",
                "name": "Vagrant",
                "commandline": "powershell.exe",
                "hidden": false,
                "icon": "C:\\Users\\xiongmeng\\Pictures\\vagrant.png",
                "startingDirectory": "E:\\Vagrant"
            },
            {
                "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
                "hidden": true,
                "name": "Azure Cloud Shell",
                "source": "Windows.Terminal.Azure"
            }
        ]
    },

    // Add custom color schemes to this array
    "schemes": [
    	    {
      "name": "Campbell",
      "foreground": "#F2F2F2",
      "background": "#0C0C0C",
      "colors": [
        "#0C0C0C",
        "#C50F1F",
        "#13A10E",
        "#C19C00",
        "#0037DA",
        "#881798",
        "#3A96DD",
        "#CCCCCC",
        "#767676",
        "#E74856",
        "#16C60C",
        "#F9F1A5",
        "#3B78FF",
        "#B4009E",
        "#61D6D6",
        "#F2F2F2"
      ]
    },
    {
      "name": "Solarized Dark",
      "foreground": "#FDF6E3",
      "background": "#073642",
      "colors": [
        "#073642",
        "#D30102",
        "#859900",
        "#B58900",
        "#268BD2",
        "#D33682",
        "#2AA198",
        "#EEE8D5",
        "#002B36",
        "#CB4B16",
        "#586E75",
        "#657B83",
        "#839496",
        "#6C71C4",
        "#93A1A1",
        "#FDF6E3"
      ]
    },
    {
      "name": "Solarized Light",
      "foreground": "#073642",
      "background": "#FDF6E3",
      "colors": [
        "#073642",
        "#D30102",
        "#859900",
        "#B58900",
        "#268BD2",
        "#D33682",
        "#2AA198",
        "#EEE8D5",
        "#002B36",
        "#CB4B16",
        "#586E75",
        "#657B83",
        "#839496",
        "#6C71C4",
        "#93A1A1",
        "#FDF6E3"
      ]
    },
    {
      "name": "Ubuntu",
      "foreground": "#EEEEEC",
      "background": "#2C001E",
      "colors": [
        "#EEEEEC",
        "#16C60C",
        "#729FCF",
        "#B58900",
        "#268BD2",
        "#D33682",
        "#2AA198",
        "#EEE8D5",
        "#002B36",
        "#CB4B16",
        "#586E75",
        "#657B83",
        "#839496",
        "#6C71C4",
        "#93A1A1",
        "#FDF6E3"
      ]
    },
    {
      "name": "UbuntuLegit",
      "foreground": "#EEEEEE",
      "background": "#2C001E",
      "colors": [
        "#4E9A06",
        "#CC0000",
        "#300A24",
        "#C4A000",
        "#3465A4",
        "#75507B",
        "#06989A",
        "#D3D7CF",
        "#555753",
        "#EF2929",
        "#8AE234",
        "#FCE94F",
        "#729FCF",
        "#AD7FA8",
        "#34E2E2",
        "#EEEEEE"
      ]
    }
    ],

    // Add any keybinding overrides to this array.
    // To unbind a default keybinding, set the command to "unbound"
    "keybindings": []
}
```