# Blueborne PoC
on Huawei Honor 4X

# Note
Be aware that on ARM code is compiled having one Byte offset after the function label due to different execution instruction sets offered on ARM chips, specifically "ARM mode" and "Thumb mode".

# Run
Make sure you have pybluez and pwntools installed:
on Ubuntu (apt-get) execute the following commands:

```
sudo apt-get install bluetooth libbluetooth-dev
sudo pip install pybluez
sudo pip install pwntools
```

# Further reading
https://www.armis.com/blueborne/
# Credits
https://github.com/ojasookert/CVE-2017-0785 for CVE-2017-0785 PoC (information leak vulnerability)



