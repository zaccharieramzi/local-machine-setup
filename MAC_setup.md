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
git config --global user.email "zaccharie.ramzi@gmail.com" &&\
git config --global push.default matching
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

## fish-like autosuggestions
(to add in plugins)
```
git clone https://github.com/zsh-users/zsh-autosuggestions \ ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

## Tree
```
brew install tree
```
## Htop
```
brew install htop
```

## Aliases
```
echo '# dev convenience
alias jn="jupyter notebook"
alias mkvenv="virtualenv -p /usr/bin/python3.6 venv"

# convenience cd
function cdvenv(){
  cd $1;
  source venv/bin/activate;
}
compdef _dirs cdvenv

# notebook pimping
alias jnbe="jupyter nbextension enable"
function jnb_ext(){
  pip install jupyter_contrib_nbextensions autopep8
  jupyter contrib nbextension install --user
  jnbe notify/notify
  jnbe snippets/main
  jnbe code_prettify/autopep8
  jnbe codefolding/main
  jnbe hinterland/hinterland
  jnbe code_prettify/isort
  jnbe splitcell/splitcell
}' >> ~/.zshrc
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
