### Install depot tools
https://commondatastorage.googleapis.com/chrome-infra-docs/flat/depot_tools/docs/html/depot_tools_tutorial.html#_setting_up
```
> git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git
> export PATH=/path/to/depot_tools:$PATH
```

```
sudo ln -s /usr/bin/python2.7 /usr/bin/python
```

https://v8.dev/docs/build

```
> gclient sync
> ./build/install-build-deps.sh
> cd /path/to/v8
> git pull && gclient sync
> tools/dev/gm.py x64.release
> tools/dev/gm.py x64.release.check
```
