# TECHSHAN AI Office

A control panel for your own Linux server — with a team of AI agents built in. It runs on your machine,
and your data stays there.

**[techshan.app](https://techshan.app)** · 30-day trial with everything · then $20 once per server, no subscription

## What it does

**The server panel** — everything you would otherwise do over SSH, in pages that show what is really on the machine.

| | |
|---|---|
| **Dashboard** | CPU, memory, temperatures, drives, network and what happened on the server, on one screen. |
| **Docker** | Containers, stacks, images, volumes, networks and registries. Logs and a shell in the browser. |
| **Virtual Machines** | Create and run KVM machines with a console in the browser, snapshots, disks and networks. |
| **Files and SMB Shares** | Browse and edit files, share folders with Windows and macOS, manage who may open them. |
| **Storage** | Drives, health, pools, encryption, network drives and NFS exports. |
| **Server settings** | Network, firewall, users, services, packages and updates, scheduled jobs, certificates, backups, logs and a terminal. |

**The AI office** — agents that take a goal, split the work and report back, using the models you choose.

- **A team of agents.** Each workspace starts with a team of seven AI agents led by an AI CEO. Give a goal; the team splits it into tasks and works on them.
- **Your models.** Connect a provider with an API key, or sign in with a plan you already pay for.
- **Chat anywhere.** Talk to an agent or a model in AI Chat, or write to your AI CEO from Telegram.

## Install

One command on the server, as root. It asks nothing, takes a few minutes, and prints the address of your panel.

```bash
curl -fsSL https://techshan.app/install.sh | sudo sh
```

**What you need:** a 64-bit Intel or AMD Linux server with systemd or OpenRC and glibc 2.34 or newer — Ubuntu 22.04
and later, Debian 12, Fedora, Rocky Linux 9, Arch, openSUSE Leap 15.6 — and root access. ARM servers and Alpine Linux
are not supported yet.

**What it does to your server:** the program goes to `/opt/techshan`, its settings to `/etc/techshan`, its data to
`/var/lib/techshan`. It uses the server's PostgreSQL (and installs it when missing), runs its own small Redis, starts
five system services and opens the panel on port 3210. No Docker is needed to run it.

**First steps**

1. Open the address the installer prints, for example `http://your-server:3210`.
2. Create your account. The first account owns the server, and the 30-day trial starts.
3. Under My Server › Settings › Server Tools, tick the tools you want the panel to manage (Docker, virtual machines, Samba…).

## Manage

```bash
techshan status         # what is running, and the version
techshan logs           # follow the logs
techshan restart
sudo techshan update    # install the newest version
techshan url <address>  # set the address the panel is opened at
```

## License

Everything works for 30 days. After that, one license is for one server: **$20, paid once**. It never expires and
includes one year of updates; the version you have keeps working afterwards, and one more year of updates is $5, only
when you want it.

- Buy it from your panel — Settings › About & License › Buy a license. The key is made for that server and the panel
  fetches it by itself.
- Without a license after the trial, the Dashboard, Docker, Virtual Machines, SMB Shares and your workspace settings
  keep working; the AI pages, Files, Storage and the server's Settings pages are locked. Nothing running on your server
  is stopped.
- New motherboard or a new server? Sign in on [techshan.app](https://techshan.app/login) and move the license to it.

## Uninstall

```bash
sudo techshan uninstall
```

It asks before it removes anything, and asks separately whether your data (database, files of the workspaces) goes
too. Containers, virtual machines, shares and files on your server are not touched.

## Support

support@techshan.app · [Terms](https://techshan.app/terms) · [Privacy](https://techshan.app/privacy)

TECHSHAN AI Office is proprietary software of TECHSHAN. © TECHSHAN
