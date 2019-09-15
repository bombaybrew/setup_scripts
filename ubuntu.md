
### OS

```
# Linux Version
> lsb_release -a

# Hostname
> hostname

# Update repo
> sudo apt-get clean 
> sudo apt-get update
> sudo apt-get upgrade
```

### GPU

```
# ubuntu-drivers devices
> lspci | grep -I VGA

# shows list of devices ( graphics card for this instance)
> prime-select query

# select prime driver
> sudo prime-select Nvidia
> sudo prime-select intel

```

### Python
```
# Python

> sudo apt-get install python3.6
> sudo apt-get install python3.7

# pyenv

> sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev

> curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash

## add to ~/.bashrc at the end of file
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"

> pyenv versions
> pyenv global 3.7.4
> pip install --upgrade pip
> python --version // 3.7.4
> pip --version // 19.2.3
```

### DataScience

```
# latest version at https://www.tensorflow.org/install/pip
> pip install tensorflow==2.0.0-rc1

> pip install -U scikit-learn
```

