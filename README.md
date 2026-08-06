<img src="logo.svg" alt="AtlasPVE" width="72" height="72" />

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
A snapshot is taken before changes, so a risky operation always has a way back.

### Live monitoring
Watch hosts, virtual machines and services live, with the metrics that matter for day to day operations.

## Why local and auditable

Atlas runs on your Proxmox host. Nothing connects in from outside, and the product works without an internet connection. Your VM, storage and network content is never sent to Atlas servers. Critical or privilege raising actions are written to an audit log with who, what, when and result. Atlas does not build a parallel permission system, it mirrors Proxmox's own user, role, group and API token model.

## Frequently asked questions

### Is Atlas open source?
The agent that runs with root privileges on the server is open under AGPL, so what it does can be read and audited. The interface and product layer are offered under a commercial license, a deliberate choice that keeps Atlas funded and maintained.

### Does Atlas replace the Proxmox web interface?
No. Atlas runs alongside Proxmox and adds a layer of safety and clarity. It keeps Proxmox as Proxmox rather than replacing it.

### Can Atlas run offline?
Yes. Atlas runs offline and continues to operate locally on the Proxmox host. The internet is used only to fetch updates and the catalog. Without it, the installed version keeps working fully.

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
