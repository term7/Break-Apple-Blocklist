# term7 - Ultimate Apple Blocklist

This AdGuard blocklist is based on:
https://theapplewiki.com/wiki/List_of_Apple_domains

**⚠️ Warning: Enabling this list will completely break most Apple services, including (but not limited to): iCloud, Apple TV+, Apple Music, Apple Arcade, Apple Maps, Apple News+, Apple Pay, App Store, iMessage, FaceTime, FindMy, etc.**

* * *

#### Allow Apple subdomains needed for critical system and security updates:

Note: The domains required for Apple system updates may vary by region.
The current allowlist has been tested and allows the system to check for and download updates. However, the update fails during the *Preparing updates…* phase. We have not yet identified the additional domains required for this step to succeed.

In the meantime, we recommend temporarily disabling the blocklist when performing system updates, and re-enabling it once the update is complete.

### **Apple macOS Update & Verification Domains Reference**

| **Domain**                        | **Purpose**                | **Explanation** |
|----------------------------------|----------------------------|-----------------|
| `mesu.apple.com`                 | Update metadata            | Checks for available macOS updates, Safari, XProtect (malware definitions), and MRT (Malware Removal Tool) updates. |
| `swscan.apple.com`              | Catalog metadata           | Works with `mesu.apple.com` to initiate update checks and fetch catalog info, including Safari updates. |
| `swdist.apple.com`              | Update distribution metadata | Provides the metadata for delta and full update packages. Tells the system where to fetch update files from. |
| `swcdn.apple.com`               | Update payloads            | Apple's CDN that hosts actual macOS update files, full installers, Safari updates, and developer tools. |
| `swcdn.g.aaplimg.com`           | CDN alias for update payloads | CNAME target of `swcdn.apple.com`, used to serve delta updates, installer packages, and system components. |
| `updates.cdn-apple.com`         | CDN entry point            | CDN routing domain for OS updates, firmware, and system installers. Resolves to Fastly or Akamai. |
| `updates.g.aaplimg.com`         | CDN intermediate           | CNAME target for `updates.cdn-apple.com`, delivering update metadata and payload pointers. |
| `download.apple.map.fastly.net`| Final CDN endpoint         | Fastly-hosted endpoint that delivers actual update payloads like macOS installers and patches. |
| `gdmf.apple.com`                | Gatekeeper trust metadata  | Stands for Gatekeeper Download Metadata Feed. Used by macOS to verify whether apps and installers are notarized and safe to run. May also be queried during update prep. |
| `gdmf.v.aaplimg.com`            | CDN alias for notarization | CNAME variant of `gdmf.apple.com`. macOS may use this as an alternative endpoint to retrieve notarization status. |
| `ocsp.apple.com`                | Certificate status check   | Used for **OCSP (Online Certificate Status Protocol)** to verify that Apple-issued certificates (used to sign apps, updates, etc.) haven’t been revoked. |
| `ocsp2.apple.com`               | Backup OCSP server         | Backup/secondary OCSP endpoint to ensure reliable certificate revocation checks. |
| `crl.apple.com`                 | Certificate revocation list| Used if OCSP fails; delivers full revocation lists (CRLs) to check whether certs are still valid. |
| `valid.apple.com`              | Certificate validation     | Verifies the validity and trustworthiness of Apple-signed assets (e.g., updates, apps). Helps validate app or system update integrity. |


* * *

If you want to use Apple Services but still block known trackers, use this list instead:
https://codeberg.org/hagezi/mirror2/raw/branch/main/dns-blocklists/adblock/native.apple.txt
