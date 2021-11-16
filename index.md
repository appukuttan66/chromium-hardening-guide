*A Guide to harden chromium-based browsers and tips to make them more secure.*
<hr>

![Github release date](https://img.shields.io/github/release-date/appukuttan66/chromium-hardening-guide?style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/appukuttan66/chromium-hardening-guide?style=flat-square)
![GitHub deployments](https://img.shields.io/github/deployments/appukuttan66/chromium-hardening-guide/github-pages?style=flat-square)


*This guide will give you tips on how to improve the security and harden Chromium-based browsers. While these work on any Chromium-based browser it is still important to use the Right one.*

## A few good Chromium-based browsers.

| Browser | Platform |
| ------- | -------- |
| [Bromite](https://bromite.org) | Android  |
| [Brave](https://brave.com)  | Android, iOS, Windows, macOS, Linux |
| [Ungoogled-Chromium](https://ungoogled-software.github.io/) | Android, Windows, macOS, Linux |

## Privacy features in `chrome://flags`

| Name | Id | Value | Platforms | Description |
| --- | --- | --- | --- | --- |
| Reduce User-Agent request header | `#reduce-user-agent` | `Enabled` | Mac, Windows, Linux, Chrome OS, Android | Reduce (formerly, "freeze") the amount of information availabfingerprinting-canvas-image-noiseer. |
| `#fingerprinting-canvas-image-data-noise` | //To do
| `#fingerprinting-client-rects-noise` | //To do
| `#fingerprinting-canvas-measuretext-noise` | //To do
| `#enable-webrtc-hide-local-ips-with-mdns` | //To do
| `#disable-webgl` | //To do
| `#enable-site-per-process` | //To do
| `#strict-orgin-isolation` | //To do
