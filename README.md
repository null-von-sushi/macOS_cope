# macOS_cope
List of recources on how to deal with macOS and make it somewhat usable.

## iMessage
You can temporarily (because it automagically comes back it seems) deregister iMessage from the share menu by running `/System/Library/Frameworks/CoreServices.framework/Versions/A/Frameworks/LaunchServices.framework/Versions/A/Support/lsregister -R -f -u /System/Applications/Messages.app`. This works on any system. A more permanent solution would be to delete iMessage (or rather, move it to a .dmg so you have a backup). For this, you will need to disable System Integrity Protection.

# SIP
[This tool](https://github.com/fxgst/writeable_root) is pretty useful for mounting rootfs as writable on Big Sur or higher...

# Finder
Download [XtraFinder](https://www.trankynam.com/xtrafinder/). This will allow normal things like Cut+Paste to work...

# Keyboard Shortcuts
Karabiner Elements

# Cloud Storage
Mountain Duck is honestly your best bet. Google Drive is especially shit, with all the extra unnecessary shortcuts. 
OneDrive's official client is alright too, if that's what you wanna use.

# Top Bar
Get [Hidden bar](https://github.com/dwarvesf/hidden)

# Alt-Tab (well, ⌘-Tab)
~~Get [Command-Tab Plus](https://noteifyapp.com/command-tab-plus/)~~~~ [AltTab](https://alt-tab-macos.netlify.app/) is free, but needs a minute or two to customize the settings. It's not hard though. 
[Contexts 3](https://contexts.co/) seems cool but is also paid software.

# 7-Zip alternative
Either [The Unarchiver](https://macpaw.com/the-unarchiver) to replace macOS built-in unarchiver, or maybe [Keka](https://www.keka.io/en/)

# Clipboard Manager
[Maccy](https://maccy.app/) is FLOSS (download page is pay-what-you-want)

# Middle Click
[MiddleClick-BigSur](https://github.com/artginzburg/MiddleClick-BigSur)

# Fix scrolling behaviour
[https://github.com/ther0n/UnnaturalScrollWheels](https://github.com/ther0n/UnnaturalScrollWheels)

# Dock
[IntelliDock](https://mightymac.app/intellidock/) provides IntelliHide for the macOS dock

# Aero Snap
[Rectangle](https://rectangleapp.com/)

# Security
## Full disk encryption without login password
 - Make two users, `macOS` and `bob` (any names will do)
 - Make the `macOS` user password the password you want to use for FDE.
 - Set any random password you want for `bob`. This will be your password after FDE is unlocked.
 - Encrypt the system, and then run `sudo fdesetup remove -user bob` and `sudo dscl . create /Users/macOS IsHidden 1`.
 - Run `pwpolicy -u macOS disableuser`
 - Log out of `macOS` and log into `bob`, then reboot. 
