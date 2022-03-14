
Command line to add to Windows Terminal for having the last Visual Studio compilwer installed on the system in 64bit with 64bit target:

```
powershell.exe -NoExit -Command "&{ $vsInstallPath=& "${env:ProgramFiles(x86)}/'Microsoft Visual Studio'/Installer/vswhere.exe" -requires "Microsoft.VisualStudio.Component.VC.Tools.x86.x64" -latest -property installationPath; Import-Module "$vsInstallPath/Common7/Tools/Microsoft.VisualStudio.DevShell.dll"; Enter-VsDevShell -VsInstallPath $vsInstallPath -Arch amd64 -HostArch amd64  -SkipAutomaticLocation }"
```
