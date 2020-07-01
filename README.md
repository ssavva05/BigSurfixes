# BigSurfixes
Big Sur fixes for unsupported Mac

to support Big Sur booting on non-APFS mac or APFS firmware mac

BigSur added the BootKernelExtensions.kc as the new kernelcache with new command kmutil

but kextcache command and prelinkedkernel are still working:

https://forums.macrumors.com/threads/macos-11-big-sur-on-unsupported-macs-thread.2242172/post-28610988

to apply the prelinkedkernel fix after BigSur Install:

diskutil apfs list

diskutil mount Preboot

Locate your BigSur Data Volume UUID

replace the "prelinkedkernel fix" file in this path:

/Volumes/UUID-BigSur/System/Library/CoreServices/

replace the "patched prelinkedkernel beta1" in this path:

/Volumes/UUID-BigSur/System/Library/PrelinkedKernels/

For the "installer fix" make a BigSur USB Installer with createinstallmedia:

sudo /Applications/Install\ macOS\ Beta.app/Contents/Resources/createinstallmedia --volume /Volumes/BigSurInstaller/

and replace this file:

/Volumes/USBInstallerBigSur/Library/Preferences/SystemConfiguration/
