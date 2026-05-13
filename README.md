# kb — knowledge base

Public notes on Linux, databases, networking, and infrastructure. The "why"
companion to [ops](https://github.com/piotraf/ops) (the "what").

Each note answers a specific question I had, fixed something I broke, or
captures a non-obvious gotcha worth remembering. Style is concise and
peer-to-peer — not tutorials.

## Layout

| Path | Scope |
|---|---|
| [db/mysql](db/mysql/) | MySQL — upgrades, recovery, tuning, Connector/J |
| [db/mariadb](db/mariadb/) | MariaDB-specific notes |
| [db/firebird](db/firebird/) | Firebird 3.x/4.x admin |
| [db/oracle](db/oracle/) | Oracle DB admin |
| [db/postgresql](db/postgresql/) | PostgreSQL admin |
| [linux/gentoo](linux/gentoo/) | Portage, USE flags, profile-specific issues |
| [linux/oracle-linux](linux/oracle-linux/) | OL 7/8/9/10 specifics |
| [linux/opensuse](linux/opensuse/) | openSUSE Leap & SLES |
| [linux/debian-ubuntu](linux/debian-ubuntu/) | Debian/Ubuntu specifics |
| [net](net/) | Networking — VLANs, switching, OPNsense, SFP/DAC |
| [virt](virt/) | Proxmox, VirtualBox, LXC, KVM |
| [homelab](homelab/) | Office lab — naming, topology, sanitized diagrams |

## Conventions

- One Markdown file per topic. Use descriptive filenames
  (`charset-conversion.md`, not `notes-2.md`).
- Cross-link freely between notes using relative paths.
- Link companion scripts in [ops](https://github.com/piotraf/ops) when
  prose explains code that lives over there.
- Date-stamp version-sensitive observations (`# Verified 2026-04-28`) so
  readers can judge staleness.

## Status

Personal notes published publicly. Accuracy reflects my best understanding
at the time of writing. Not a substitute for vendor documentation.

## License

[CC BY 4.0](LICENSE) — credit appreciated, derivatives welcome.
