# term7 - Ultimate Apple Blocklist

This AdGuard blocklist is based on:
https://theapplewiki.com/wiki/List_of_Apple_domains

**⚠️ Warning: Enabling this list will completely break most Apple services, including (but not limited to): iCloud, Apple TV+, Apple Music, Apple Arcade, Apple Maps, Apple News+, Apple Pay, App Store, iMessage, FaceTime, FindMy, etc.**

* * *

#### Allow Apple subdomains needed for critical system and security updates:

Note: The domains required for Apple system updates may vary by region.
The current allowlist has been tested and confirmed to work for devices in Central Europe, but you may need to adjust it based on your geographic location to ensure updates function correctly.

1. **mesu.apple.com**
- Checks for macOS, Safari, MRT, and XProtect updates.
- Checks for Safari version updates (on macOS).
2. **swscan.apple.com**
- Initiates update check!
- Metadata for Safari updates are also scanned here.
3. **swdist.apple.com**
- Download full and delta macOS update packages.
- Downloads updates for macOS, Safari, security patches.
4. **updates.cdn-apple.com**
- Distributes OS updates, firmware, and installer packages.
5. **swcdn.apple.com**
- Hosts update files, installers, and developer tools.
6. **swcdn.g.aaplimg.com**
- Backend domain for macOS/iOS updates, often reached via CDN redirection.
- Delivers firmware, delta updates, and installer packages.
7. **gdmf.apple.com**
- gdmf = Gatekeeper Download Metadata Feed.
- Checks whether an app is notarized and safe to open.
- When opening apps for the first time, it checks their trust status.
- Verifies if a downloaded app has been approved and notarized.
- Checks notarization of app installers during install.
- Some system update components use gdmf to verify trust before allowing an update to proceed.
7. **gdmf.v.aaplimg.com**
- gdmf = Gatekeeper Download Metadata Feed.
- macOS uses either gdmf.apple.com or gdmf.v.aaplimg.com.

* * *

If you want to use Apple Services but still block known trackers, use this list instead:
https://codeberg.org/hagezi/mirror2/raw/branch/main/dns-blocklists/adblock/native.apple.txt
