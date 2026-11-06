# ssbu-nextendo

A Skyline/Ozone plugin that puts Super Smash Bros. Ultimate
online on the [Nextendo](https://nextendo.network) servers, from emulators that don't connect to
Nextendo on their own (such as Eden).

## Requirements

- Super Smash Bros. Ultimate updated to **13.0.5**
- [Skyline](https://github.com/skyline-dev/skyline/releases) or [Ozone](https://github.com/WuBoytH/ozone/releases) installed for the game
- A Nextendo account, signed in with the official
  [citron-nextendo](https://nextendo.network) build

If you play on citron-nextendo itself, you don't need this plugin: it connects to Nextendo by
itself.

> [!WARNING]
> **Don't use this plugin on a real Switch: you risk a ban.** To play on Nextendo from a
> console, use [Nextendo Prelude](https://github.com/NextendoNetwork/Prelude-Nro) instead.

## Installation

In the paths below, `sd:/` is your emulator's SD card folder (in most emulators: *File → Open
SD card folder*, or `sdmc/` in its data folder).

1. Download `libssbu_nextendo.nro` from the [Releases](../../releases) page.
2. Copy it to `sd:/atmosphere/contents/01006A800016E000/romfs/skyline/plugins/`.
3. Set up your account (below).

## Account setup

1. In citron-nextendo, sign in to your Nextendo account. citron-nextendo saves your login in
   `nextendo_account.txt`, in its config folder:
   - Windows: `%APPDATA%\citron\config\nextendo_account.txt`
   - Linux: `~/.config/citron/nextendo_account.txt`
   - Portable install: `user/config/nextendo_account.txt` next to the citron executable
2. Copy that file to your emulator's SD card as `sd:/ultimate/nextendo/config.txt`
   (create the `ultimate/nextendo` folders if they don't exist).

The file looks like this:

```
pid=1800000000
username=someone
friend_code=...
token=...
```

This file holds your account's session token: don't share it.

Without this file, the plugin does nothing and the game stays offline as usual.

**If you can't log in:**

- Make sure your Nextendo account has **both an email and a Discord account linked**: the
  servers refuse accounts without them.
- If it worked before, your token has probably expired: sign in again in citron-nextendo and
  copy the new `nextendo_account.txt` over `config.txt`.

## Options

Addionally, you can add these optional lines to `config.txt`:

| Line                | What it does                                                    |
| ------------------- | --------------------------------------------------------------- |
| `log=1`             | Logs what the plugin does to `sd:/ultimate/nextendo/log.txt`    |
| `server_ip=<ip>`    | Uses another game server than Nextendo's default                |
| `nat_ip=<ip>`       | Uses another NAT check server than Nextendo's default           |

## Troubleshooting

- **The game doesn't go online**: check that the game is on 13.0.5, that Skyline is loading
  (other Skyline plugins work), and that `config.txt` is at the right path.
- **Something else is wrong**: add `log=1` to `config.txt`, try again, and include
  `sd:/ultimate/nextendo/log.txt` when you report the problem. The log does not contain your
  token, but check it before you post it publicly.
