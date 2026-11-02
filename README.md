<div align="center">

<img src="snap/gui/picgo.png" alt="PicGo logo" width="128" />

# PicGo

**Upload images to image hosts and copy the Markdown link**

[![picgo](https://snapcraft.io/picgo/badge.svg)](https://snapcraft.io/picgo)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64 and arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [PicGo](https://github.com/Molunerfinn/PicGo), a desktop app that uploads pictures, screenshots and clipboard images to image hosts and returns their links.

</div>

---

## Getting Started

<a href="https://snapcraft.io/picgo"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install picgo
picgo
```

You can also launch PicGo from the application menu. Typora, Obsidian, VS Code and other editors upload through its server on `http://127.0.0.1:36677`.

## Configure

Use the application's settings. There are no `snap set` options.

```bash
sudo snap connect picgo:removable-media    # optional: upload from /media, /mnt
```

The configuration, upload history, plugins and caches are stored in `~/snap/picgo/common`. Plugins are installed from npm inside the snap.

## Limitations

- Files must be in your home directory or connected removable storage. Hidden folders in your home directory are not accessible.
- Plugins that compile native code during installation are not supported. Plugins run on the Node.js built into Electron.
- The start at login setting has no effect. Global shortcuts may not work in Wayland sessions.
- An existing native installation's configuration in `~/.config/picgo` is not imported. Application updates are managed by snapd.

## Build

```bash
git clone https://github.com/sidalit/picgo-snap.git
cd picgo-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/picgo-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/Molunerfinn/PicGo/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/picgo-snap/blob/main/LICENSE).
