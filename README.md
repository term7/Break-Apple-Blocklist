# term7 - Ultimate Apple Blocklist

This AdGuard blocklist is based on:
https://theapplewiki.com/wiki/List_of_Apple_domains

It will more or less disconnect all Apple Services. It will feel like you are partly offline (no AppleMusic Store, no Apple Weather Updates, no AppStore, no Updates...), while normal browsing in Firefox, etc. will still work.

We allow Apple subdomains responsible for system updates:

1. mesu.apple.com
- Checks for macOS, Safari, MRT, and XProtect updates.
- Checks for Safari version updates (on macOS).
2. swscan.apple.com
- Initiates update check!
- Metadata for Safari updates are also scanned here.
3. swdist.apple.com
- Download full and delta macOS update packages.
- Downloads updates for macOS, Safari, security patches.
4. gdmf.apple.com
- gdmf = Gatekeeper Download Metadata Feed.
- Checks whether an app is notarized and safe to open.
- When opening apps for the first time, it checks their trust status.
- Verifies if a downloaded app has been approved and notarized.
- Checks notarization of app installers during install.
- Some system update components use gdmf to verify trust before allowing an update to proceed.
5. gdmf.v.aaplimg.com
- gdmf = Gatekeeper Download Metadata Feed.
- macOS uses either gdmf.apple.com or gdmf.v.aaplimg.com.

If you want to use Apple Services but still block known trackers, use this list instead:
https://codeberg.org/hagezi/mirror2/raw/branch/main/dns-blocklists/adblock/native.apple.txt
