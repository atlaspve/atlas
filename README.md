<img src="logo.png" alt="AtlasPVE" width="96" height="96" />

# AtlasPVE

**The safe operations layer for Proxmox.**

AtlasPVE is a safe operations layer for Proxmox VE that runs on your own host. It brings virtual machines, LXC containers, storage, networking, safe updates, backups and self-hosted services into one interface, and it makes your Proxmox VE infrastructure local, visible, auditable and safely manageable.

Website: [atlaspve.com](https://atlaspve.com) · Live demo: [demo.atlaspve.com](https://demo.atlaspve.com)

## Who it is for

Homelab users, self-hosters, small teams and service providers who run Proxmox VE and want a clearer, safer way to operate it, without giving up Proxmox itself and without sending data to a cloud.

## The problem it solves

- Dense Proxmox tables, where storage and network relationships are hard to see.
- The risk of a host not booting after a kernel update.
- Opening SSH and forwarding a port just to reach a single VM.
- Destructive storage or network changes with no preview and no easy way back.

## What Atlas does

### Guided storage and network operations
Storage and network changes run through a guided flow with an operation preview and rollback awareness, across ZFS, LVM and Btrfs.

### Safe updates
Every update's dependencies, effects and changelog are shown up front, with boot protection so a kernel update does not leave the host unbootable.

### SSH-free VM access
Reach an in-VM terminal, file browser and live metrics with no SSH and no open port.

### Virtual machines and containers
Create and manage KVM virtual machines and LXC containers with wizards for the common setups.

### Backups and rollback
Before an update runs, a snapshot is taken, so a kernel or package change has a way back. Backup jobs, snapshots and restores are managed from the same interface.

### Live monitoring
Watch hosts, virtual machines and services live, with the metrics that matter for day to day operations.

## Why local and auditable

Atlas runs on your Proxmox host. Nothing connects in from outside, and the product works without an internet connection. Your VM, storage and network content is never sent to Atlas servers. Critical or privilege raising actions are written to an audit log with who, what, when and result. Atlas does not build a parallel permission system, it mirrors Proxmox's own user, role, group and API token model.

## Frequently asked questions

### Is Atlas open source?
Partly, and deliberately so. The agent that runs with root privileges on the host is AGPL licensed and installs as readable source under /opt/atlas/agent, so it can be inspected on the machine it runs on. This repository carries the project overview, not that source. The analysis engine and the interface are proprietary, a choice that keeps Atlas funded and maintained.

Why not publish it here as well? The reason is not only commercial. Atlas runs inside other people's infrastructure, and publishing every line also publishes a map for anyone scanning for a way in. In an age of automated scanning that risk lands on the customer, not on the vendor. Reading the code on the machine where it runs gives the same assurance without handing that map to everyone at once. Responsibility does not move either way: a hole in Atlas is ours, and closing it is ours.

### The agent runs as root. What limits the damage?

The agent needs root because most of what it does sits below the Proxmox API: apt, kernel, bootloader, mount, zpool, passthrough. Being open source does not offset that on its own, so the separation is architectural rather than textual. The product and analysis layer does not run as root; it runs under its own user with service level restrictions, reachable only locally, and it refuses to start if launched as root. Atlas does not invent its own authorization; the user's real Proxmox permissions are read at login, every request is checked in one place before routing, and if no rule matches a write falls to the strictest bar. Commands never go through a shell, arguments are passed separately. Privileged actions are written to an audit log. Guests are reached over the guest agent socket rather than SSH, so no port is opened and no password is left inside the guest.

### Does Atlas replace the Proxmox web interface?
No. Atlas runs alongside Proxmox and adds a layer of safety and clarity. It keeps Proxmox as Proxmox rather than replacing it.

### Can Atlas run offline?
Yes. Atlas runs offline and continues to operate locally on the Proxmox host. The internet is used for updates, the application catalog, license checks and, if you enable it, notifications to your account. Without it, the installed version keeps working fully.

### Does Proxmox data pass through Atlas servers?
No. The Atlas management layer runs inside your own infrastructure. VM, storage and network content is not sent to Atlas servers.

### Which storage types are supported?
Atlas works with common Proxmox storage, including ZFS, LVM and Btrfs.

### Do my Proxmox users and roles still apply?
Yes. Atlas mirrors Proxmox's own user, role, group and API token model. Proxmox decides who can see and do what, and Atlas follows it.

### What happens if I do not renew updates?
Nothing gets locked. The installed local version keeps working. Only new features, security patches and compatibility updates for new Proxmox releases stop. When renewal is enabled again, update access returns.

### Is this a subscription, or am I buying the license?
You are buying, not renting. The version you paid for runs indefinitely. If you do not renew, that version keeps running. Annual renewal covers new versions and update access.

## Links

- Website: [atlaspve.com](https://atlaspve.com)
- Live demo: [demo.atlaspve.com](https://demo.atlaspve.com)
- Account portal: [portal.atlaspve.com](https://portal.atlaspve.com)
- Security: report issues to security@atlaspve.com
