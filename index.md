
![GitHub last commit](https://img.shields.io/github/last-commit/appukuttan66/chromium-hardening-guide?style=flat-square)
![GitHub deployments](https://img.shields.io/github/deployments/appukuttan66/chromium-hardening-guide/github-pages?style=flat-square)


*This guide will give you tips on how to improve the security and harden Chromium-based browsers. While these work on any Chromium-based browser it is still important to use the Right one.*

## A few good Chromium-based browsers.

| Browser | Platform |
| ------- | -------- |
| [Bromite](https://bromite.org) | Android  |
| [Brave](https://brave.com)  | Android, iOS, Windows, macOS, Linux |
| [Ungoogled-Chromium](https://ungoogled-software.github.io/) | Android, Windows, macOS, Linux |

<hr>

Chromium based browsers are not as configurable as Firefox but you still have a few good options available.

## Privacy features in `chrome://flags`

Go to [chrome://flags](chrome://flags) and search for the `Names` or `Ids`, then set or make sure the values match.

| Name | Id | Value | Platforms | Description | Reason |
| --- | --- | --- | --- | --- | --- |
| Reduce User-Agent request header | `#reduce-user-agent` | `Enabled` | Mac, Windows, Linux, Chrome OS, Android | Reduce (formerly, "freeze") the amount of information available. | User-Agents in chrome reveals a lot more info about the OS and browser than Firefox |
| WebGL |`#disable-webgl` | `Disabled` | Windows, Linux, Chrome OS, Android | Enable or disable all versions of WebGL | Every Browser renders WebGL Objects in a slightly different way and this is commonly used to fingerprint Browsers. ( may break 3d models and some browser games ) |
| Disable Canvas image data fingerprint deception | `#fingerprinting-canvas-image-data-noise` | `Enabled` | Mac, Windows, Linux, Chrome OS, Android | Slightly modifies at most 20 pixels in Canvas image data extracted via JS APIs | Canvas is a really common way to fingerprint |
| Disable get*ClientRects() fingerprint deception | `#fingerprinting-client-rects-noise` | `Enabled` | Mac, Windows, Linux, Chrome OS, Android | Scale the output values of Range::getClientRects() and Element::getBoundingClientRect() with a randomly selected factor in the range -0.0003% to 0.0003%, which are recomputed on every document initialization. | Canvas Fingerprinting |
| Disable Canvas::measureText() fingerprint deception | `#fingerprinting-canvas-measuretext-noise` | `Enabled` | Mac, Windows, Linux, Chrome OS, Android | Scale the output values of Canvas::measureText() with a randomly selected factor in the range -0.0003% to 0.0003%, which are recomputed on every document initialization. | Canvas fingerprinting |
| Anonymize local IPs exposed by WebRTC. |`#enable-webrtc-hide-local-ips-with-mdns` | `Enabled` | Mac, Windows, Linux, Chrome OS | Conceal local IP addresses with mDNS hostnames. | This is the best we have to prevent WebRTC from leaking IPs. Doesn't disable WebRTC though. |
| Strict site isolation |`#enable-site-per-process` | `Enabled` | Android | Security mode that enables site isolation for all sites (SitePerProcess). In this mode, each renderer process will contain pages from at most one site, using out-of-process iframes when needed. Check chrome://process-internals to see the current isolation mode. Setting this flag to 'Enabled' turns on site isolation regardless of the default. | Runs each site as a different process. |
| Strict-Orgin-Isolation | `#strict-orgin-isolation` | `Enabled` | Mac, Windows, Linux, Chrome OS, Android | Experimental security mode that strengthens the site isolation policy. Controls whether site isolation should use origins instead of scheme and eTLD+1. | Site-isolation |


## Disclaimer

*Some of the settings are experimental and may break some websites. Try these at your own risk, I shall not be liable if something goes wrong.*
