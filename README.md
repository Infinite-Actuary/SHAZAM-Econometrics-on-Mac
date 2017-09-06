# Installing [SHAZAM 11.1.4](http://www.econometrics.com/download/) (32 bit) on macOS Sierra

## Show Hidden Files in Finder
* This step isn't required but makes navigating installation directories easier
* From the [Terminal](https://en.wikipedia.org/wiki/Terminal_(macOS)) run command: `defaults write com.apple.finder AppleShowAllFiles YES`
* Hold `option/alt` key and right click to relaunch Finder

## Allow [Gatekeeper](https://support.apple.com/en-us/HT202491) to run unsigned packages
* As specified on [WineHQ](https://wiki.winehq.org/MacOS)
* From Terminal `sudo spctl --master-disable`
* System Preferences > Security & Privacy > General Tab > Select Anywhere
![Gatekeeper](https://upload.wikimedia.org/wikipedia/en/e/eb/Gatekeeper.png)

## Install [XQuartz](https://www.xquartz.org/) 2.7.11
* Requires logout after installing (~190 MB total)
* Applications > Utilities > [XQuartz](https://en.wikipedia.org/wiki/XQuartz)

## Install latest version of [Wine Stable 2.0.2](https://dl.winehq.org/wine-builds/macosx/download.html) .pkg
* Select 64 bit support (~520 MB total)


