
Command line to add to Windows Terminal for having the last Visual Studio compilwer installed on the system in 64bit with 64bit target:

```
powershell.exe -NoExit -Command "&{ $vsInstallPath=& "${env:ProgramFiles(x86)}/'Microsoft Visual Studio'/Installer/vswhere.exe" -requires "Microsoft.VisualStudio.Component.VC.Tools.x86.x64" -latest -property installationPath; Import-Module "$vsInstallPath/Common7/Tools/Microsoft.VisualStudio.DevShell.dll"; Enter-VsDevShell -VsInstallPath $vsInstallPath -Arch amd64 -HostArch amd64  -SkipAutomaticLocation }"
```
Note that recent version of Windows Terminal + Visual Studio will do that for you automatically (finally!) Just make sure it's really the 64bit compiler invoking the 64bit target being selected.


To enable git-bash `ln -s` symbolic link creation on Windows, add this in the `~/.bashrc`
```
# Enable symlinks
export MSYS=winsymlinks:nativestrict
```

