Place both files in the Root Directory of your bootable installation flash drive (recommend going to  Ninite before hand and selecting some of the programs you normally install https://ninite.com/)& download your drivers before hand or at least a the network adapter you are using
Explanation for MikeZAakaHopGoblinDebloatWindows
List of apps to remove: The script defines a list of applications to remove.
Remove-App function: This function removes each app for all users and removes the provisioned package to prevent reinstallation.
Disable automatic driver installation: This part of the script sets a registry key to prevent Windows from automatically installing drivers.
Basic system optimizations:
Disable Xbox Game Bar: Disables the Game DVR and Game Bar.
Disable Background Apps: Disables all background apps.
Set Power Plan to High Performance: Sets the power plan to High Performance.
Disable Startup Delay: Removes the startup delay for applications.
Disable Windows Tips: Disables Windows tips notifications.
Clean up temp files: Deletes temporary files from Windows and user temp directories.

list of Apps removed
{
"Microsoft.BingNews",
    "Microsoft.GetHelp",
    "Microsoft.Getstarted",
    "Microsoft.Messaging",
    "Microsoft.MicrosoftOfficeHub",
    "Microsoft.MicrosoftSolitaireCollection",
    "Microsoft.NetworkSpeedTest",
    "Microsoft.News",
    "Microsoft.Office.Lens",
    "Microsoft.Office.OneNote",
    "Microsoft.Office.Sway",
    "Microsoft.OneConnect",
    "Microsoft.People",
    "Microsoft.Print3D",
    "Microsoft.SkypeApp",
    "Microsoft.Office.Todo.List",
    "Microsoft.Whiteboard",
    "Microsoft.WindowsAlarms",
    "Microsoft.WindowsFeedbackHub",
    "Microsoft.WindowsMaps",
    "Microsoft.XboxSpeechToTextOverlay",
    "Microsoft.ZuneMusic",
    "Microsoft.ZuneVideo",
    "*EclipseManager*",
    "*ActiproSoftwareLLC*",
    "*AdobeSystemsIncorporated.AdobePhotoshopExpress*",
    "*Duolingo-LearnLanguagesforFree*",
    "*PandoraMediaInc*",
    "*CandyCrush*",
    "*BubbleWitch3Saga*",
    "*Wunderlist*",
    "*Flipboard*",
    "*Twitter*",
    "*Facebook*",
    "*Spotify*",
    "*Minecraft*",
    "*Royal Revolt*",
    "*Sway*",
    "*Speed Test*",
    "*Dolby*"
)
}


Explanation for autounattend.xml

Pass: windowsPE: Configures settings for the Windows Preinstallation Environment (WinPE).
Setup language and locale: Sets the UI, input, system, and user locale to en-US.
ImageInstall: Specifies the image index to install, disk, and partition to install to.
UserData: Accepts the EULA and sets default user data.
EnableFirewall: Disables the firewall during setup (can be re-enabled later if needed).
Pass: offlineServicing: Runs commands while Windows is offline.
RunSynchronousCommand: Runs the PowerShell script (MikeZAakaHopGoblinDebloatWindows.ps1) from the flash drive.
Pass: specialize: Customizes settings after Windows installation.
FirstLogonCommands: Runs the PowerShell script again after the first logon to ensure all customizations are applied.
Steps to Ensure Correct Implementation
Check Script File Path: Ensure MikeZAakaHopGoblinDebloatWindows.ps1 is copied to the root of the bootable flash drive.