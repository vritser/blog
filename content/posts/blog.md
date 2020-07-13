+++
title = "Homebrew"
author = ["vritser"]
draft = false
+++

## Install Homebrew {#install-homebrew}

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Check if Homebrew is installed and working properly.

```sh
brew -v
```


## Use USTC Mirro {#use-ustc-mirro}

**Homebrew Core**

```sh
# replace brew.git
cd "$(brew --repo)"
git remote set-url origin https://mirrors.ustc.edu.cn/brew.git

# replace homebrew-core.git
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
```

**Bottles**

For bash user

```sh
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile
```

For zsh user

```sh
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```

**Reset**

```sh
# reset brew.git
cd "$(brew --repo)"
git remote set-url origin https://github.com/Homebrew/brew.git

# reset homebrew-core.git
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://github.com/Homebrew/homebrew-core.git
```


## Usage {#usage}

```sh

# Search package
brew search emacs

# Use regular
brew search /^vi/

# Install package
brew install emacs

# Install graphics package
brew cask install google-chrome

# Uninstall package
brew uninstall emacs

# Upgrade package
brew upgrade emacs

# Update brew
brew update

# List installed packages
brew list

```


## Tap {#tap}

Use tap to extends brew.

```sh
brew tap d12frosted/emacs-plus
brew install emacs-plus
```


## Services {#services}

We can use brew to manage services.

```sh
# List all services
brew services [list]

# Run the service formula without registering to launch at login (or boot).
brew services run emacs

# Start the service formula immediately and register it to launch at login (or boot).
brew services start redis

# Stop the service formula immediately and unregister it from launching at login (or boot).
brew services stop redis

# Stop (if necessary) and start the service formula immediately and register it to launch at login (or boot).
brew services restart redis

# Remove all unused services.
brew services cleanup
```
