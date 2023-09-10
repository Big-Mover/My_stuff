1. Change boot order in bios to use USB (might also need to remove drive containing old installation)
3. Boot from Windows 10 USB Key drive
4. Set up as private (not organisation) pro account
5. Activate in CMD/powershell:
  ```powershell
  slmgr /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX
  slmgr /skms kms8.msguides.com
  slmgr /ato
  ```
6. Activate Microsoft Office by:
     Method 1 - PowerShell (Recommended)
     On Windows 8.1/10/11, right-click on the Windows start menu and select PowerShell or Terminal (Not CMD).
     Copy-paste the below code and press enter
     ```powershell
     irm https://massgrave.dev/get | iex
     ```
     You will see the activation options, and follow onscreen instructions.
     That's all.

     Otherwise follow instructions [here](https://github.com/massgravel/Microsoft-Activation-Scripts).
   
7. Install Chrome, Office (University account), steam, whatsapp, signal, vlc, battlenet, epicgames...
8. To remove dual boot menu on startup: https://neosmart.net/wiki/remove-dual-boot-menu/
9. To remove signin screen -> Option 2: https://www.isunshare.com/windows-10-password/remove-sign-in-password-on-windows-10-computers.html
10. Turn off/hide OneDrive personal: https://answers.microsoft.com/en-us/msoffice/forum/all/how-to-turn-offhide-onedrive-personal-but-leave/bea35a10-78e9-4b35-a5df-c69060ad509b
