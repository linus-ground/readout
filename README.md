# Readout

Readout is a small menu bar app for macOS that shows the current state of your Mac at a glance: CPU, memory, disks (internal and external), network traffic, and power.

This repository is used for distribution only. It contains no source code. Installers (DMG) are published under [Releases](https://github.com/linus-ground/readout/releases), and the website and update feed are served from [GitHub Pages](https://linus-ground.github.io/readout/).

## Requirements

- A Mac with Apple silicon (M1 or later)
- macOS 26 Tahoe or later

Intel-based Macs are not supported.

## Installation

1. Download `Readout-x.y.z.dmg` from the [latest release](https://github.com/linus-ground/readout/releases/latest).
2. Open the disk image and drag Readout into the Applications folder.
3. Launch Readout from the Applications folder. A gauge icon appears in the menu bar.

## Usage

- **Click** the menu bar icon to open a panel with CPU, memory, network, power, and every mounted disk with its free space.
- **Click a tile** (CPU, memory, network, or power) to see the top 10 or 20 apps or processes using it. Switch between apps (helper processes combined) and individual processes; processes owned by other users are marked **System** and are hidden unless you uncheck **Hide system**. Press ‹ or Esc to go back.
- **Right-click** for quick options: icon only or metrics in the menu bar, refresh interval, check for updates, settings, and quit.
- In **Settings** you can choose which metrics appear in the menu bar and in what order, the refresh interval (30 seconds to 15 minutes), network volumes, opening at login, and the language (Korean or English).

Readout is designed to stay out of the way. In icon-only mode (the default) it reads nothing in the background; values are read only while the panel is open. In metrics mode it refreshes the menu bar at the interval you choose. Disk capacity is never polled in the background, so sleeping external hard drives are not woken.

Power is the whole-system power draw reported by macOS, averaged over about a minute. In the power list, each app is ranked by its CPU energy; macOS does not report energy for processes owned by other users, so those are not listed there.

The top lists are read only while a list is on screen, refreshing every 3 seconds, and stop as soon as you go back or close the panel.

## Updates

Readout checks for updates once a day using [Sparkle](https://sparkle-project.org). When a new version is available, Readout shows a prompt; choosing **Install Update** downloads, verifies, and installs it, then relaunches the app. To check manually, right-click the menu bar icon and choose **Check for Updates…**, or click **Check for Updates…** next to the version in Settings. Automatic checks can be turned off in Settings.

Settings are preserved across updates.

## License

Readout is distributed under the [PolyForm Noncommercial License 1.0.0](LICENSE.md). It may be used and shared freely for noncommercial purposes, such as personal use, study, research, and use by noncommercial organizations. Commercial use is not permitted.

Third-party components and their licenses are listed in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

## Repository contents

| Path | Description |
|------|-------------|
| `docs/index.html` | Website (GitHub Pages) |
| `docs/appcast.xml` | Update feed read by the app. Each release is signed with an EdDSA key, and the app installs only updates whose signature matches. |
| `LICENSE.md` | License |
| `THIRD-PARTY-NOTICES.md` | Third-party notices |
