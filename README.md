# MacOs

### Enable Touch ID for sudo
```
cd /etc/pam.d
sudo cp sudo_local.template sudo_local
sudo nano sudo_local
```
In that file, navigate to the line that contains with pam_tid.so and delete the hashtag (#) at the beginning. Save the file out by pressing Control-X, typing ‘Y’ to save your changes, and hitting Return.
### TextEdit: Use Plain Text Mode as Default
```bash
defaults write com.apple.TextEdit RichText -int 0
```
### Avoid creating .DS_Store files on network or USB volumes
```bash
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true
defaults write com.apple.desktopservices DSDontWriteUSBStores -bool true
```
### Disable auto-correct
```bash
defaults write -g NSAutomaticSpellingCorrectionEnabled -bool false
```
### Finder: allow quitting via ⌘ + Q; doing so will also hide desktop icons
```bash
defaults write com.apple.finder QuitMenuItem -bool true && killall Finder
```
### Disable the crash reporter
```
defaults write com.apple.CrashReporter DialogType -string "none"
```
### Disable Siri telemetry
```
defaults write com.apple.assistant.support 'Siri Data Sharing Opt-In Status' -int 2
```
### Disable potential DNS leaks
 ```
 sudo defaults write /Library/Preferences/com.apple.mDNSResponder.plist NoMulticastAdvertisements -bool YES
```
### Disable the sound effects on boot
 ```
sudo nvram SystemAudioVolume=" "
sudo nvram StartupMute=%01
 ```
###  Disable opening and closing window animations
```
defaults write NSGlobalDomain NSAutomaticWindowAnimationsEnabled -bool false
```
###  Disable smart quotes and dashes as they’re annoying when typing code
```
defaults write NSGlobalDomain NSAutomaticQuoteSubstitutionEnabled -bool false
defaults write NSGlobalDomain NSAutomaticDashSubstitutionEnabled -bool false
```
### Finder: show all filename extensions
```
defaults write NSGlobalDomain AppleShowAllExtensions -bool true
```
### Finder: show status bar
```
defaults write com.apple.finder ShowStatusBar -bool true
```
### Finder: show path bar
```
defaults write com.apple.finder ShowPathbar -bool true
```
### Keep folders on top when sorting by name
```
defaults write com.apple.finder _FXSortFoldersFirst -bool true
```
### Disable disk image verification
```
defaults write com.apple.frameworks.diskimages skip-verify -bool true
defaults write com.apple.frameworks.diskimages skip-verify-locked -bool true
defaults write com.apple.frameworks.diskimages skip-verify-remote -bool true
```

### Always open everything in Finder's list view.
### Use list view in all Finder windows by default
### Four-letter codes for the other view modes: `icnv`, `clmv`, `Flwv`
```
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"
```
### Disable the warning before emptying the Trash
```
defaults write com.apple.finder WarnOnEmptyTrash -bool false
```
### Disable hot corners
```
defaults write com.apple.dock wvous-tl-corner -int 0
defaults write com.apple.dock wvous-tr-corner -int 0
defaults write com.apple.dock wvous-bl-corner -int 0
defaults write com.apple.dock wvous-br-corner -int 0
```
### Don't show recently used applications in the Dock
```
defaults write com.Apple.Dock show-recents -bool false
```
### Only use UTF-8 in Terminal.app
```
defaults write com.apple.terminal StringEncodings -array 4
```