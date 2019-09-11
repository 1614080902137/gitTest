================================================================
# Auto Renewal:

To install this solution for auto renewal activation, run these scripts respectively:

1-SppExtComObjPatcher.cmd
install/uninstall the Patcher Hook.

2-Activate-Local.cmd
activate installed supported products (you must run it at least once).
you may need to run it again if you installed Office product afterwards.

================================================================
# Manual:

To only activate without installing and without renewal, run this script only:

KMS_VL_ALL.cmd

you will need to run it again before the activation period expire (6 months by default).

================================================================
# Windows 10 KMS 2038:

Both KMS_VL_ALL.cmd and Activate-Local.cmd are set by default
to check and skip Windows activation if KMS 2038 detected

However, if you would like to revert or use normal KMS activation:
- edit KMS_VL_ALL.cmd or 2-Activate-Local.cmd with Notepad
- change KMS38=1 to zero 0
- save the script, and run it as administrator

================================================================
# Online KMS:

You may use Activate-Local.cmd for online activation,
if you have valid/trusted external KMS host server.

- edit Activate-Local.cmd with Notepad
- change KMS_IP=172.16.0.2 to the IP/address of online KMS server
- change Online=0 from zero 0 to 1
- save the script, and run it as administrator

================================================================
# Setup Preactivate:

- To preactivate the system during installation, copy $oem$ to "sources" folder in the installation media (iso/usb)

- If you already use another setupcomplete.cmd, rename this one to KMS_VL_ALL.cmd or similar name
then add a command to run it in your setupcomplete.cmd, example:
call KMS_VL_ALL.cmd

- Use SppExtComObjPatcher.cmd if you want to uninstall the project afterwards.

- Note: setupcomplete.cmd is disabled if the default installed key for the edition is OEM Channel

================================================================
# Remarks:

- Some security programs will report infected files, that is false-positive due KMS emulating.
- Remove any other KMS solutions. Temporary turn off AV security protection. Run as administrator.
- If you installed the solution for auto renewal, exclude this file in AV security protection:
C:\Windows\system32\SppExtComObjHook.dll

================================================================
# KMS Options for advanced users:

You can modify KMS-related options by editing SppExtComObjPatcher.cmd or KMS_VL_ALL.cmd or setupcomplete.cmd

- KMS_Emulation
Enable embedded KMS Emulator functions
never change this option

- KMS_RenewalInterval
Set interval (minutes) for activated clients to auto renew KMS activation
this does not affect the overall KMS period (6 months)
allowed values: from 15 to 43200

- KMS_ActivationInterval
Set interval (minutes) for products to attempt KMS activation, whether unactivated or failed activation renewal
this does not affect the overall KMS period (6 months)
allowed values: from 15 to 43200

- KMS_HWID
Set custom KMS host Hardware ID hash, 0x prefix is mandatory
only affect Windows 8.1/10

- Windows, Office2010, Office2013, Office2016, Office2019
Set custom fixed KMS host ePID for each product, instead generating it randomly

================================================================
# Debug:

If the activation failed, you may run the debug mode to help determining the reason

move SppExtComObjPatcher-kms folder to a short path
with Notepad open/edit KMS_VL_ALL.cmd
change the zero 0 to 1 in set _Debug=0
save the script, and run it as administrator
wait until command prompt window is closed and Debug.log is created
then upload or copy/post the log file

Note: this will auto remove SppExtComObjPatcher if it was installed

================================================================
# Supported Volume Products:

Windows 7-8-8.1-10
Windows Server 2008R2-2012-2012R2-2016-2019
Office  2010-2013-2016-2019

================================================================
# Credits:

cynecx         - SppExtComObj Injector
qad            - SppExtComObjPatcher
Mouri_Naruto   - SppExtComObjPatcher-DLL
CODYQX4        - KMSEmulator Source
MasterDisaster - initial script / WMI methods
qewpal         - KMS-VL-ALL author
abbodi1406     - KMS_VL_ALL-SppExtComObjPatcher-kms author

thanks for special assistance:
NormieLyfe, Nucleus, Enthousiast, rpo
