# term7 - Ultimate Apple Blocklist

This AdGuard blocklist is based on:
https://theapplewiki.com/wiki/List_of_Apple_domains

Apple is known to implement strong privacy features in its products. Nevertheless, certain forms of user tracking still occur. This article explores how Apple collects data despite its emphasis on privacy: https://gizmodo.com/apple-iphone-analytics-tracking-even-when-off-app-store-1849757558

**⚠️ Warning: Enabling this list will completely break most Apple services, including (but not limited to): iCloud, Apple TV+, Apple Music, Apple Arcade, Apple Maps, Apple News+, Apple Pay, App Store, iMessage, FaceTime, FindMy, etc.**

* * *

#### Allow Apple subdomains needed for critical system and security updates:

Note: The domains required for Apple system updates may vary by region.
The current allowlist has been tested and allows the system to check for and download updates.

### **Apple macOS Update & Verification Domains Reference**

| **Domain**                        | **Purpose**                  | **Explanation** |
|----------------------------------|------------------------------|-----------------|
| `mesu.apple.com`                 | Update metadata              | Checks for available macOS updates, Safari, XProtect (malware definitions), and MRT (Malware Removal Tool) updates. |
| `swscan.apple.com`              | Catalog metadata             | Works with `mesu.apple.com` to initiate update checks and fetch catalog info, including Safari updates. |
| `swdist.apple.com`              | Update distribution metadata | Provides the metadata for delta and full update packages. Tells the system where to fetch update files from. |
| `swcdn.apple.com`               | Update payloads              | Apple's CDN that hosts actual macOS update files, full installers, Safari updates, and developer tools. |
| `swcdn.g.aaplimg.com`           | CDN alias for update payloads | CNAME target of `swcdn.apple.com`, used to serve delta updates, installer packages, and system components. |
| `updates.cdn-apple.com`         | CDN entry point              | CDN routing domain for OS updates, firmware, and system installers. Resolves to Fastly or Akamai. |
| `updates.g.aaplimg.com`         | CDN intermediate             | CNAME target for `updates.cdn-apple.com`, delivering update metadata and payload pointers. |
| `download.apple.map.fastly.net`| Final CDN endpoint           | Fastly-hosted endpoint that delivers actual update payloads like macOS installers and patches. |
| `cds.apple.com`                 | Delta & support file delivery| Serves delta updates, support files, and miscellaneous content used during system update processing. |
| `lcdn-locator.apple.com`        | CDN optimization lookup      | Helps Apple choose the best local CDN node to download updates from, improving speed and reliability. |
| `gdmf.apple.com`                | Gatekeeper trust metadata    | Gatekeeper Download Metadata Feed. Used by macOS to verify whether apps and installers are notarized and safe to run. May also be queried during update prep. |
| `gdmf.v.aaplimg.com`            | CDN alias for notarization   | CNAME variant of `gdmf.apple.com`. macOS may use this as an alternative endpoint to retrieve notarization status. |
| `ocsp.apple.com`                | Certificate status check     | Used for **OCSP (Online Certificate Status Protocol)** to verify that Apple-issued certificates (used to sign apps, updates, etc.) haven’t been revoked. |
| `ocsp2.apple.com`               | Backup OCSP server           | Backup/secondary OCSP endpoint to ensure reliable certificate revocation checks. |
| `crl.apple.com`                 | Certificate revocation list  | Used if OCSP fails; delivers full revocation lists (CRLs) to check whether certs are still valid. |
| `valid.apple.com`              | Certificate validation       | Verifies the validity and trustworthiness of Apple-signed assets (e.g., updates, apps). Helps validate app or system update integrity. |



* * *

If you want to use Apple Services but still block known trackers, use this list instead:
https://codeberg.org/hagezi/mirror2/raw/branch/main/dns-blocklists/adblock/native.apple.txt

***

# **MIRRORS**

This repository is actively maintained on Codeberg:<br>
https://codeberg.org/term7/Break-Apple-Blocklist

Changes are pushed regularly to our Github Mirror:<br>
https://github.com/term7/Break-Apple-Blocklist