# fml — Fix My Laptop

A lightweight Linux system maintenance tool built for low-spec and older machines.

## Install

### Manual
```bash
sudo curl -o /usr/local/bin/fml https://raw.githubusercontent.com/Melangert/Fix-My-Laptop-FML-/main/usr/bin/fml
sudo chmod +x /usr/local/bin/fml
```

## Usage

```bash
fml              # Interactive menu
fml status       # Show load, memory, and disk
fml top          # Top CPU and memory processes
fml clean        # Remove unused packages and caches
fml boost        # Toggle CPU power mode
fml health       # Health check with warnings
fml temps           Check hardware temperatures
fml --help
fml --version
```

## Power Mode Toggle

`fml boost` toggles between **power-saver** and **performance** mode.

- **power-saver** — less heat, better battery life, recommended for everyday use on low-spec machines
- **performance** — maximum CPU speed, useful for short intensive tasks

Run `fml boost` once to switch to performance, run it again to switch back.
Works with `powerprofilesctl`, `tuned-adm`, and `cpupower` — whichever is available on your system.

## Cleanup

`fml clean` safely removes:
- Unused packages (apt/dnf/pacman/zypper)
- Unused Flatpak runtimes and old Snap revisions
- Thumbnail and browser caches
- Your temp files from /tmp
- System journal logs older than 7 days

Always asks for confirmation before making any changes. Never touches your personal files or documents.

## Supported package managers

| Manager | Distros |
|---------|---------|
| apt     | Debian, Ubuntu, Mint, Pop!_OS |
| dnf     | Fedora, RHEL, CentOS Stream |
| pacman  | Arch, Manjaro, EndeavourOS |
| zypper  | openSUSE |

## Requirements

- bash 4.0+
- procps (`free`, `ps`)
- Nothing else — no Python, no Node, no heavy dependencies

## License

MIT — Kevin Melangert
