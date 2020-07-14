### Wifi signal strength
```
while x=1; do /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport -I | grep CtlRSSI; sleep 1; done
```
