# UWPHook

See https://github.com/BrianLima/UWPHook

This is just a hack to:
- filter to all games (w/ PowerShell tweaks)
- always select all games (UI tweaks)

I wrote down my ideas/notes on [this UWPHook issue](https://github.com/BrianLima/UWPHook/issues/64#issuecomment-1646875329)
This hack is good enough for me - but may not be perfectly accurate, and may not be good enough for you!

## Local development setup / build

See https://github.com/BrianLima/UWPHook/issues/79#issuecomment-1646893289 for some tips on getting set up

If you build a "Release" version, access it at:
C:\Users\yourName\codeProjects\UWPHook\UWPHook\bin\Release. You should see the folder inside Visual Studio anyhow.

## Premade downloads

tldr; don't exist, not happening
You can see all the source code changes VS the main repo, and build it yourself.
If you want this hacky version then follow the above steps.

## Recommended usage

- Uninstall the official UWPHook.
- Create a runnable .exe, and configure it as you like
- Edit GamesWindow.xaml.cs, turning the line `/// Application.Current.Shutdown();` into `Application.Current.Shutdown();`. 
    - UWPHook will do its magic, restart Steam, and then close itself
- Follow either/both the following `Run` sections


### Run on startup
- Create a Release .exe (see above)
- Right click the .exe, and make a shortcut
- Move the shortcut to %appdata%\Microsoft\Windows\Start Menu\Programs\Startup

### Run from Steam Big Picture

- Open Steam
- Click `Games` at the top
- Click `Add a Non-Steam game to my Library...`
- Browse for `UWPHook.exe - Shortcut`, or the actual executable `.......UWPHook\UWPHook\bin\Release\UWPHook.exe`
- Check `UWPHook.exe - Shortcut`
- Click `Add selected programs`

## TODO

### "recently played" always replaced

Should filter games which are already in Steam
Ideally ask Steam about this (via AUMID?)
Alternatively, have some file store of the games list (name or AUMID?), and only add what isn't in there. 
If there's nothing to add, don't restart Steam