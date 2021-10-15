# Install Chrome
```
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
open https://github.com/settings/ssh/new
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
git clone https://github.com/zsh-users/zsh-autosuggestions \ ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
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
alias mkvenv="virtualenv -p /usr/bin/python3.6 venv"
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

# Atom
```
sudo add-apt-repository ppa:webupd8team/atom &&\
sudo apt update &&\
sudo apt install atom &&\
apm install --package-file atom_package_list.txt &&\
git config --global core.editor "atom"
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
sudo add-apt-repository ppa:jonathonf/python-3.6 &&\
sudo apt-get update &&\
sudo apt-get install python3.6 python3-distutils python3.6-dev &&\
sudo apt-get install python
```

## pip
```
curl https://bootstrap.pypa.io/get-pip.py > get-pip.py &&\
sudo python get-pip.py &&\
rm get-pip.py
```

## virtualenv
```
sudo pip install virtualenv
```

# Spotify
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 931FF8E79F0876134EDDBDCCA87FF9DF48BF1C90 &&\
echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list &&\
sudo apt-get update &&\
sudo apt-get install spotify-client
```

# Slack
```
wget https://downloads.slack-edge.com/linux_releases/slack-desktop-4.12.2-amd64.deb &&\
sudo dpkg -i slack-desktop-4.12.2-amd64.deb
```
