# APPLE OFFLINE

This AdGuard blocklist is based on:
https://theapplewiki.com/wiki/List_of_Apple_domains

It will more or less disconnect all Apple Services. It will feel like you are partly offline (no AppleMusic Store, no Apple Weather Updates, no AppStore, no Updates...), while normal browsing in Firefox, etc. will still work.

We allowed a few Apple subdomains responsible for system updates:

mesu.apple.com → Checks for updates.<br>
swcdn.apple.com / swdownload.apple.com / swcdn.g.aaplimg.com → Downloads updates.<br>
appldnld.apple.com → macOS installer downloads.<br>
oscdn.apple.com → Content Delivery for updates.<br>
gdmf.apple.com → Firmware updates.<br>
gs.apple.com → Firmware signing (important for installing updates).

If you want to use Apple Services but still block known trackers, use this list instead:
https://codeberg.org/hagezi/mirror2/raw/branch/main/dns-blocklists/adblock/native.apple.txt
