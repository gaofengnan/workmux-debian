![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/gaofengnan/workmux-debian/total)
![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/gaofengnan/workmux-debian/latest/total)
![GitHub Release](https://img.shields.io/github/v/release/gaofengnan/workmux-debian)
![GitHub Release Date](https://img.shields.io/github/release-date/gaofengnan/workmux-debian)

<h1>
   <p align="center">
     <a href="https://workmux.raine.dev/"><img src="https://github.com/gaofengnan/workmux-debian/blob/main/workmux.svg" alt="workmux Logo" width="128" style="margin-right: 20px"></a>
     <a href="https://www.debian.org/"><img src="https://github.com/gaofengnan/workmux-debian/blob/main/debian-logo.png" alt="Debian Logo" width="104" style="margin-left: 20px"></a>
     <br>workmux for Debian
   </p>
</h1>
<p align="center">
 workmux orchestrates git worktrees and tmux windows for zero-friction parallel development.
</p>

# workmux for Debian

> Fork of [dariogriffo/workmux-debian](https://github.com/dariogriffo/workmux-debian) (MIT); the original packaging is by Dario Griffo. Served at [deb.gaofn.xyz](https://deb.gaofn.xyz) for Debian 12 (bookworm) and 13 (trixie).

This repository contains build scripts to produce the _unofficial_ Debian packages
(.deb) for [workmux](https://github.com/raine/workmux/) hosted at [deb.gaofn.xyz](https://deb.gaofn.xyz)

Currently supported Debian distros are:
- Bookworm (v12)
- Trixie (v13)
- Forky (v14)
- Sid (testing)

Currently supported Ubuntu distros are:
- Jammy (22.04)
- Noble (24.04)
- Questing (25.10)
- Resolute (26.04)

Supported architectures:
- amd64 (x86_64) - All distributions
- arm64 (aarch64) - All distributions

Upstream publishes no i386, armel, armhf or riscv64 binaries, so those
architectures are not available.

The packages include the workmux binary and shell completions for bash, fish
and zsh. Upstream ships no man page; run `workmux docs` for the full
documentation and `workmux --help` for the command reference.

> ℹ️ workmux drives a terminal multiplexer, so the package **depends on `git`**
> and **recommends `tmux`**. tmux is the default backend but kitty, WezTerm and
> Zellij are supported alternatives, which is why it is a recommendation rather
> than a hard dependency.

This is an unofficial community project to provide a package that's easy to
install on Debian. If you're looking for the workmux source code, see
[workmux](https://github.com/raine/workmux/).

## Install/Update

### The Debian way

```sh
sudo install -d -m 0755 /etc/apt/keyrings
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.gpg -o /etc/apt/keyrings/deb.gaofn.xyz.gpg
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.sources -o /etc/apt/sources.list.d/deb.gaofn.xyz.sources
# Debian 12 (bookworm): fetch deb.gaofn.xyz-bookworm.sources instead
sudo apt update
sudo apt install -y workmux
```

### Manual Installation

1. Download the .deb package for your Debian version available on
   the [Releases](https://github.com/gaofengnan/workmux-debian/releases) page.
2. Install the downloaded .deb package.

```sh
sudo dpkg -i <filename>.deb
```
## Updating

To update to a new version, just follow any of the installation methods above. There's no need to uninstall the old version; it will be updated correctly.

## Building

### Build for single architecture
```sh
./build.sh <workmux_version> <build_version> <architecture>
# Example: ./build.sh 0.1.243 1 arm64
```

### Build for all architectures
```sh
./build.sh <workmux_version> <build_version> all
# Example: ./build.sh 0.1.243 1 all
```

## Roadmap

- [x] Produce a .deb package on GitHub Releases
- [x] Set up a debian mirror for easier updates
- [x] Multi-architecture support (amd64, arm64)

## Disclaimer

- This repo is not open for issues related to workmux. This repo is only for _unofficial_ Debian packaging.
