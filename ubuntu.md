
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

### Disk

```
> df      // report file system disk space usage
> lsblk   // list block devices
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

# Ubuntu 18.04
sudo apt-add-repository -r ppa:graphics-drivers/ppa
sudo apt install nvidia-driver-430
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
> python --version  // 3.7.4
> pip --version     // 19.2.3
```

### DataScience

```
// latest version at https://www.tensorflow.org/install/pip
pip install tensorflow==2.0.0
pip install tensorflow-gpu==2.0.0     // GPU version
pip install -U scikit-learn
pip install numpy
pip install pandas
pip install scipy
pip install matplotlib
pip install scrapy
pip install --upgrade gensim
pip install missingno
```

### Juypter Notebook
```
> pip install jupyter
> jypter notebook // localhost only.
> jupyter notebook --ip x.x.x.x --port 8888 // x.x.x.x - local ip of server.
```

