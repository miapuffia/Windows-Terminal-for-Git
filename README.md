# Windows-Terminal-for-Git
Replaces the MinGW Git Bash window with Windows Terminal

1. Add the Git Bash profile to Windows Terminal. This can be edited in Settings -> Open JSON file

I used the folowing:

```javascript
"profiles": 
{
    [
        ...
        {
            "acrylicOpacity": 0.75,
            "background": "#000000",
            "closeOnExit": "graceful",
            "colorScheme": "GitBash",
            "commandline": "\"%PROGRAMFILES%\\git\\bin\\bash.exe\" --login -i -l",
            "cursorColor": "#FFFFFF",
            "cursorShape": "bar",
            "font": 
            {
                "face": "Consolas",
                "size": 10
            },
            "guid": "{00000000-0000-0000-0000-000000012345}",
            "historySize": 9001,
            "icon": "%PROGRAMFILES%\\git\\mingw64\\share\\git\\git-for-windows.ico",
            "name": "Git Bash",
            "padding": "0, 0, 0, 0",
            "snapOnInput": true,
            "useAcrylic": true
        }
        ...
    ]
},
"schemes": 
[
    ...
    {
        "background": "#000000",
        "black": "#0C0C0C",
        "blue": "#6060FF",
        "brightBlack": "#767676",
        "brightBlue": "#3B78FF",
        "brightCyan": "#61D6D6",
        "brightGreen": "#16C60C",
        "brightPurple": "#B4009E",
        "brightRed": "#E74856",
        "brightWhite": "#F2F2F2",
        "brightYellow": "#F9F1A5",
        "cursorColor": "#FFFFFF",
        "cyan": "#3A96DD",
        "foreground": "#BFBFBF",
        "green": "#00A400",
        "name": "GitBash",
        "purple": "#BF00BF",
        "red": "#BF0000",
        "selectionBackground": "#FFFFFF",
        "white": "#FFFFFF",
        "yellow": "#BFBF00"
    },
    ...
]
```

2. Make sure the `guid` field in the Git Bash profile is not used in any of your other Windows Terminal profiles
3. In your Registry Editor navigate to `HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Directory\background\shell\git_shell\command`
4. Edit the default value to `"wt.exe" -d "%v." -p "Git Bash"`

The change should be immediate.
