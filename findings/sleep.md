
## ThinkPad T14s Gen 1 AMD

### high suspend power consumption

with s2idle, the battery lost 14840 mWh within 23 hours
which means 645 mW

with deep sleep, the power consumption is 860 mW

### deep sleep: late time sync

when waking up from deep sleep, it takes ~ 10 seconds for time to sync up
this is true both in command line (date command) and system tray applet


