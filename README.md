# Installing [SHAZAM 11.1.4](http://www.econometrics.com/download/) (32 bit) on macOS Sierra

## Show Hidden Files in [Finder](https://en.wikipedia.org/wiki/Finder_(software))
* This step isn't required but makes navigating installation directories easier
* From the /Applications/Utilities/[Terminal](https://en.wikipedia.org/wiki/Terminal_(macOS)) run command: `defaults write com.apple.finder AppleShowAllFiles YES`
* Hold `option/alt` key and right click to relaunch Finder

## Allow [Gatekeeper](https://support.apple.com/en-us/HT202491) to temporarily run unsigned packages
* As specified on [WineHQ](https://wiki.winehq.org/MacOS)
* From Terminal run command: `sudo spctl --master-disable`
* System Preferences > Security & Privacy > General Tab > Select Anywhere
![Gatekeeper](https://upload.wikimedia.org/wikipedia/en/e/eb/Gatekeeper.png)
* See [tekrevue](https://www.tekrevue.com/tip/gatekeeper-macos-sierra/) for example
* After completing installation steps revert Gatekeeper back to previous configuration
* From Terminal run command: `sudo spctl --master-disable`

## Install [XQuartz](https://www.xquartz.org/) 2.7.11
* Requires logout after installing (~190 MB total)
* Applications > Utilities > [XQuartz](https://en.wikipedia.org/wiki/XQuartz)

## Install latest version of [Wine Stable 2.0.2](https://dl.winehq.org/wine-builds/macosx/download.html).pkg
* Select 64 bit support (~520 MB total)
* Applications > Wine Stable > Launch
* This should open a new Terminal where wine is on the [System PATH](https://en.wikipedia.org/wiki/PATH_(variable))
* `which wine` > **/Applications/Wine Stable.app/Contents/Resources/wine/bin/wine**
* WINE_PREFIX = /Users/{user_name}/.wine

## Install SHAZAM 32 bit
* Run the [Windows Installer](https://en.wikipedia.org/wiki/Windows_Installer) (.msi)
```Bash
cd ~/Downloads
wine msiexec /i SHAZAM_11_1_4_32.msi
```
* Allow the installation of [Mono](https://wiki.winehq.org/Mono) & [Gecko](https://wiki.winehq.org/Gecko) packages
* Follow default directories
```Bash
cd /Users/{user_name}/.wine/drive_c/SHAZAM
wine SHAZAMW.exe
```
* Error: *fixme:ntdll:NtLockFile I/O completion on lock not implemented yet*
* SHAZAM 64 bit suffered from page faults on read access while trying to run ~~SHAZAM Example~~
* create [alias](https://en.wikipedia.org/wiki/Alias_(Mac_OS)) in ~/.bash_profile
```Bash
alias shazam='wine /Users/{user_name}/.wine/drive_c/SHAZAM/SHAZAMW.exe
```
* See [alias example](https://coolestguidesontheplanet.com/make-an-alias-in-bash-shell-in-os-x-terminal/) for more detail
* You should now be able to launch SHAZAM by simply opening a Terminal and running `shazam`
* You can also navigate to the SHAZAM directory **/Users/{user_name}/.wine/drive_c/SHAZAM** in Finder > Open With > Enable: All Applications > Wine Stable
* Drag this folder to the [favorites sidebar](https://support.apple.com/kb/PH19079?locale=en_US) for easier access

