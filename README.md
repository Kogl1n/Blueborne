# BlueBorne PoC (CVE-2017-0781)
on Huawei Honor 4X

# What is it?
A company called Armis published a PoC of a family of RCE Bluetooth vulnerabilities (not only but here limited to Android). They called it BlueBorne.

# Why hasn't it been in the wild?
The reason this exploit hasn't been seen in public use is that it requires information leak about the location of libraries in the victim's memory via the information leak vulnerability (CVE-2017-0785) since different phone models have different libraries due to compiling. With that information one can overcome the ASLR quite easily because there are no other methods of stack protection in use like a stack canary.

# Note
Be aware that on ARM code is compiled having one Byte offset after the function label due to different execution instruction sets offered on ARM chips, specifically "ARM mode" and "Thumb mode".



# Debugging apps or processes that crash
If you want debuggerd to suspend crashed processes so you can attach gdb, set the appropriate property:
## Android 7.0 Nougat and later.
adb shell setprop debug.debuggerd.wait_for_gdb true
## Android 6.0 Marshmallow and earlier.
adb shell setprop debug.db.uid 999999
At the end of the usual crash output, debuggerd provides instructions on how to connect gdb using the command:
gdbclient PID
https://source.android.com/devices/tech/debug/gdb

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
https://github.com/ArmisSecurity/blueborne for the research and extensive code 



