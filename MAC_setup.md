# Install brew
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
This requires approval and password
# Install brew cask
```
brew tap caskroom/cask
```
# Install Chrome
```
brew cask install google-chrome
```
This requires password
# SSH key
## Generate it
```
mkdir ~/.ssh &&\
ssh-keygen -t rsa -b 4096 -C "zaccharie.ramzi@gmail.com" -q -N "" -f ~/.ssh/id_rsa &&\
eval "$(ssh-agent -s)" &&\
ssh-add ~/.ssh/id_rsa
```
## Add it to Github Account
```
cat ~/.ssh/id_rsa.pub | pbcopy &&\
open https://github.com/settings/ssh/new
```
# Download this file
```
mkdir -p ~/workspace/gists_and_docs &&\
cd ~/workspace/gists_and_docs &&\
git clone git@github.com:zaccharieramzi/local-machine-setup.git
```
# Settings
Make docker show up and hide automatically
Use Google calendar in mac calendar : https://support.google.com/calendar/answer/99358?hl=en
# Install Atom
```
brew cask install atom &&\
apm install --packages-file atom_package_list.txt
```
# Install Slack
```
brew cask install slack
```
# Configure git
```
brew install git-lfs &&\
git config --global user.name "Zaccharie Ramzi" &&\
git config --global user.email "zaccharie@xbird.io"
```
# Terminal
## Zsh and oh-my-zsh
```
brew install zsh zsh-completions zsh-syntax-highlighting &&\
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh &&\
chsh -s /usr/local/bin/zsh
```
This requires password
## iTerm2
```
brew cask install iterm2
```
### Preferences
- In Keys, set Hotkey and [follow this website](https://coderwall.com/p/ds2dha/word-line-deletion-and-navigation-shortcuts-in-iterm2) for useful shortcuts.
- In Profiles, set window transparency (1/3), and style to Full-width, top of the screen.
- In Advanced/Hotkey, set "If the only window open is a hotkey window"
## Tree
```
brew install tree
```
## Htop
```
brew install htop
```
# Python
```
brew install python3
```
## pip
```
curl https://bootstrap.pypa.io/get-pip.py > get-pip.py &&\
sudo python get-pip.py &&\
rm get-pip.py
```
This requires password
## virtualenv
```
sudo pip install virtualenv
```
This requires password

# Docker
https://docs.docker.com/docker-for-mac/install/
```
brew cask install kitematic
```
# Leisure
## Spotify
```
brew cask install spotify
```
### Spotmenu
```
brew cask install spotmenu
```
