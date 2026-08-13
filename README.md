# aurora-tlp

**aurora-tlp** is a custom bootable container ([bootc](https://github.com/bootc-dev/bootc)) image based on Universal Blue's [Aurora](https://getaurora.dev/) (Fedora KDE Plasma). It enhances battery efficiency and system thermal management on laptops by replacing default power utilities (`power-profiles-daemon` and `tuned`) with [TLP](https://linrunner.de/tlp/).

## Image Variants

- **`:latest`** — Standard Aurora image pre-configured with TLP power management.
- **`:dx`** — Aurora Developer Experience (DX) image with TLP power management alongside built-in developer tools (e.g. Podman Desktop, VS Code, docker-cli).

---

## How to Rebase

To switch your existing Fedora Atomic or Universal Blue system to `aurora-tlp`, execute one of the following commands in your terminal:

### Standard Variant (`:latest`)

```bash
sudo bootc switch ghcr.io/clientsiderz/aurora-tlp:latest
```

### Developer Experience Variant (`:dx`)

```bash
sudo bootc switch ghcr.io/clientsiderz/aurora-tlp:dx
```

### Apply Changes

Reboot your system to apply the rebase:

```bash
sudo systemctl reboot
```

### Verify Installation

After rebooting, check that TLP is active and managing system power:

```bash
sudo tlp-stat -s
```
