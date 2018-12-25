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
mkdir ~/.ssh
ssh-keygen -t rsa -b 4096 -C "zaccharie.ramzi@gmail.com" -q -N "" -f ~/.ssh/id_rsa
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

## Add it to Github Account
```
cat ~/.ssh/id_rsa.pub
open http://github.com
```

# Install and configure git
```
sudo apt-get install git
git config --global user.name "Zaccharie Ramzi"
git config --global user.email "zaccharie.ramzi@gmail.com"
```

# Terminal
## Zsh and oh-my-zsh
```
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
This requires password
## iTerm2
