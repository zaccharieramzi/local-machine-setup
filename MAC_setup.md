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
# SSH keys
## Generate it
```
mkdir ~/.ssh
ssh-keygen -t rsa -b 4096 -C "zaccharie.ramzi@gmail.com" -q -N "" -f ~/.ssh/id_rsa
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```
## Add it to Github Account
```
cat ~/.ssh/id_rsa.pub | pbcopy
open http://github.com
```
# Download this file
```
mkdir -p ~/workspace/gists_and_docs
cd ~/workspace/gists_and_docs
git clone git@github.com:zaccharieramzi/local-machine-setup.git
```
