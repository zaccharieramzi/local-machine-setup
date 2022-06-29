# Install Chrome
```
sudo sh -c 'echo "deb [arch=amd64] https://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list' && \
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add - && \
sudo apt-get update && \
sudo apt-get install google-chrome-stable
```

# Install curl
```
sudo apt-get install curl
```

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
cat ~/.ssh/id_rsa.pub &&\
xdg-open https://github.com/settings/ssh/new
```

# Install and configure git
```
sudo apt-get install git &&\
git config --global user.name "Zaccharie Ramzi" &&\
git config --global user.email "zaccharie.ramzi@gmail.com" &&\
git config --global push.default matching
```

## Create global gitignore
```
git config --global core.excludesfile ~/.gitignore &&\
touch ~/.gitignore &&\
echo 'venv' >> ~/.gitignore &&\
echo 'personal_experiments' >> ~/.gitignore &&\
echo '.vscode/' >> ~/.gitignore &&\
echo '.ipynb_checkpoints' >> ~/.gitignore
```

# Terminal
## Zsh and oh-my-zsh
```
sudo apt-get install zsh &&\
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" &&\
chsh -s `which zsh`
```

## fish-like autosuggestions
(to add in plugins)
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

## Tree
```
sudo apt-get install tree
```

## Htop
```
sudo apt-get install htop
```

## Aliases
```
echo '# dev convenience
alias jn="jupyter notebook"
alias mkvenv="python3 -m venv venv"
alias mkvenv9="python3.9 -m venv venv"
alias tb='tensorboard --logdir=./logs'
alias tbdev='tensorboard dev upload --logdir logs'

# convenience cd
function cdvenv(){
  cd $1;
  source venv/bin/activate;
}
compdef _dirs cdvenv

# debug pytest
function pytest_debug(){
  pytest -xs $1 --pdb --pdbcls=IPython.terminal.debugger:Pdb
}
compdef '_files -g "*.py"' pytest_debug

function pyprofile(){
  python -m cProfile $1
}
compdef '_files -g "*.py"' pyprofile

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

# VSCode
```
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt update
sudo apt-get install code
```

# Python
```
sudo apt update &&\
sudo apt install software-properties-common &&\
sudo add-apt-repository ppa:deadsnakes/ppa &&\
sudo apt install python3.9 python3.9-dev python3.9-venv python3.9-distutils python3-pip
```

# Spotify, Slack, Bitwarden Mattermost
```
sudo snap install spotify slack bitwarden mattermost-desktop skype zoom-client
```

# Vim
```
sudo apt install vim
```

# Mendeley
```
wget https://static.mendeley.com/bin/desktop/mendeley-reference-manager-2.73.0-x86_64.AppImage &&\
chmod +x mendeley-reference-manager-2.73.0-x86_64.AppImage &&\
./mendeley-reference-manager-2.73.0-x86_64.AppImage
```
