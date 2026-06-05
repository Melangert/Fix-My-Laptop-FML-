# fml — Fix My Laptop

A lightweight Linux system maintenance tool built for low-spec and older machines, doesnt magically imporve performance but it would be good to run it every once in a while if you feel your system slowing down.

![fml screenshot](fml.png)

## Install
```bash

git clone https://github.com/Melangert/Fix-My-Laptop-FML-.git
cd Fix-My-Laptop-FML-

sudo cp ./fml /usr/local/bin/fml
sudo chmod +x /usr/local/bin/fml
fml --help
```
or with the tar release cd into install directory then
```bash
tar -xzf extract.tar.gz
sudo install -m 755 fml /usr/local/bin/fml

```


## Requirements
-any supported Linux distribution
-Bash

## How to use

Run `fml` to open the interactive menu.

### Commands

- `fml status` — Show CPU load, memory usage, and disk usage.
- `fml top` — Display the highest CPU and memory consuming processes.
- `fml clean` — Remove unused packages and caches.
- `fml boost` — Toggle between performance and power-saving modes.
- `fml health` — Run a system health check.
- `fml temps` — Display hardware temperatures.
- `fml fix` — Attempt to fix detected issues automatically.
- `fml suggest` — Show recommendations based on your system.
- `fml monitor` — Live system monitoring view.

Example:


fml status
fml clean --dry-run
## Power Mode Toggle

`fml boost` toggles between power-saverand performancemode.

-power-saverdecreases performance but preserves battery health
-performance maximum CPU speed, useful for shorter tasks.

Run `fml boost` once to switch to performance and run  it again to switch back.
Works with `powerprofilesctl` `tuned-adm`   and `cpupower`.

## Cleanup 

`fml clean` removes:
- unused system packages
- Unused flatpak runtimes and oldsnap revisions
- Thumbnail and browser caches
- Your temp files from /tmp
- System journal logs older than a week

Always asks for confirmation from you before making any changes. fml will  never touch your personal files or documents.

## Supported package managers

| Manager | 
|---------|
| apt     | 
| dnf     | 
| pacman  |
| zypper  |

  
## License

MIT — Kevin Melangert



## Credits
Used AI to debug clean function and add temps and health.
