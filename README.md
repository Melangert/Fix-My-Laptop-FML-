# fml — Fix My Laptop

A lightweight Linux maintenance tool for older and low-resource machines. It reports system health and offers interactive cleanup and power-profile controls.

## Requirements

- Linux
- Bash 4 or newer
- Standard system utilities: `awk`, `df`, `free`, `ps`
- Optional tools are detected automatically: `sudo`, package managers, `flatpak`, `snap`, `powerprofilesctl`, `tuned-adm`, and `cpupower`

## Install

Install from a local checkout:

```bash
git clone https://github.com/Melangert/Fix-My-Laptop-FML-.git
cd Fix-My-Laptop-FML-
sudo install -m 755 fml /usr/local/bin/fml
fml --help
```

Or download `fml-linux.tar.gz` from the [Releases page](https://github.com/Melangert/Fix-My-Laptop-FML-/releases), extract it, and install the script:

```bash
tar -xzf fml-linux.tar.gz
sudo install -m 755 fml /usr/local/bin/fml
```

## Commands

| Command | Description |
| --- | --- |
| `fml` | Open the interactive menu |
| `fml status` | Show load, memory, disk, and uptime |
| `fml top` | List the busiest processes |
| `fml health` | Check load, RAM, disk, and swap pressure |
| `fml temps` | Show available thermal sensor readings |
| `fml suggest` | Print recommendations based on current metrics |
| `fml fix` | Review detected issues and offer actions |
| `fml boost` | Toggle the available performance profile |
| `fml monitor` | Refresh status and suggestions every two seconds |
| `fml clean --dry-run` | Preview eligible cleanup targets |
| `fml clean` | Review and confirm cleanup actions |

## Cleanup behavior

Cleanup asks before making changes. It can clear package-manager caches, unused Flatpak runtimes, disabled Snap revisions, thumbnail and browser caches, and system journal entries older than seven days. Temporary files in `/tmp` are eligible only when they belong to the current user and are more than seven days old. Close browsers before clearing their caches.

Use `fml clean --dry-run` to inspect approximate sizes first. Estimates are best-effort and may vary while applications are running.

## Power profiles

`fml boost` uses the first available controller among `powerprofilesctl`, `tuned-adm`, and `cpupower`. The requested change may be unavailable if the system does not support that profile or requires elevated permissions.

## License

MIT. See [LICENSE](LICENSE).
