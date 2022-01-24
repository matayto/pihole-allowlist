# pihole-allowlist

Small set of allows that are in addition to allowlists at https://github.com/anudeepND/whitelist

Many streaming services rely on trackers to provide their services, and pihole can cause odd streaming issues when trying to play media, e.g., videos start but hang with spinner going forever, etc.

Common Sense Media did research into the privacy of streaming apps and devices, and they compiled a list of third-party domains for many streaming platforms. Most of the streaming services require at least one of these domains to be allowed in pihole for the service to function correctly. This document is available here: https://www.commonsensemedia.org/sites/default/files/uploads/research/privacy_of_streaming_apps_and_devices-final.pdf. Check out 'App Traffic Analysis'.

## Disable pihole on a single device

Assuming pihole is acting as the DHCP server, add a custom dnsmasq entry to provide static DHCP for the affected client(s) and set a tag with a custom resolver configuration.

Example:

```
dhcp-option=tag:nopihole,option:dns-server,1.1.1.3,1.0.0.3
dhcp-host=AA:BB:CC:11:22:33,192.168.1.20,work-laptop,set:nopihole
```
