# How to install a Mac - for Devs

1. Open Terminal.app


2. Set mac configs:
  a. Dock settings
    ```
    defaults write com.apple.dock tilesize -int 38
    defaults write com.apple.dock autohide -int 1
    defaults write com.apple.finder ShowHardDrivesOnDesktop -int 1
    defaults write com.apple.finder ShowExternalHardDrivesOnDesktop -int 1
    defaults write com.apple.finder ShowRemovableMediaOnDesktop -int 1
    defaults write com.apple.finder NewWindowTarget PfHm
    defaults write -g AppleShowAllExtensions -int 1
    ```

  b. Keyboard settings
  ```
  defaults write -g InitialKeyRepeat -int 100
  defaults write -g KeyRepeat -int 60
  defaults write -g AppleKeyboardUIMode -int 2
  ```

  c. Accessibility settings  
  Go to Preferences > Accessibility > Zoom: enable **Use scroll gesture with modifier...**

  d. Set initial audio volume (for silent boot without sound)
  ```
  sudo /usr/sbin/nvram SystemAudioVolume=%01
  ```

  e. Log out of your mac to apply all configurations ;)


3. Set up git with ssh
  a. Install git using osx: Type `git` into your terminal

  b.
    ```
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_rsa
    pbcopy < ~/.ssh/id_rsa.pub
    ```

  c. go to github.com and paste the copied public key from your clipboard

  d. Test connection:
    ```
    ssh -T git@github.com
    ```


4. Set up git with https:
  a.
    ```
    git credential-osxkeychain
    ```

  b. clone a repository with https. you have to enter your github passwort if you do this the first time.


5. Install brew: http://brew.sh
  ```
  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```

6. Install hub
  ```
  brew install hub
  ```

7. Setup your shell
  a. set default shell
    ```
    chsh -s /bin/zsh
    ```
  b. create profile files
    ```
    touch ~/.zshrc ~/.zshenv
    ```
    or for bash:
    ```
    touch ~/.profile
    ```
  c. Download some nice terminal fonts:
    ```
    hub clone powerline/fonts && cd fonts && ./install.sh
    ```

8. Install cask: http://caskroom.io
  ```
  brew install caskroom/cask/brew-cask
  brew tap caskroom/homebrew-versions
  ```

9. Install apps:  
  a.    
    ```
    brew cask install iterm2 google-chrome sublime-text3 flashlight kitematic bettertouchtool dropbox evernote quicklook-json skype hipchat mou the-unarchiver
    ```

  b. install some quicklook plugins:

    ```
    brew cask install qlcolorcode qlstephen qlmarkdown quicklook-json qlprettypatch quicklook-csv betterzipql qlimagesize webpquicklook suspicious-package
    ```


10. Install node using nvm: https://github.com/creationix/nvm
  ```
  curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.25.4/install.sh | bash
  nvm install iojs
  nvm default iojs
  ```

11. Install sublime package control
