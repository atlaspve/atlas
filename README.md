# AtlasPVE

**The safe operations layer for Proxmox.**

AtlasPVE is a safe operations layer for Proxmox VE, running on your own host. It brings VMs, storage, network, safe updates, backups and self-hosted services into one interface, and it makes your Proxmox VE infrastructure local, visible, auditable and safely manageable.

Website: [atlaspve.com](https://atlaspve.com) · Live demo: [demo.atlaspve.com](https://demo.atlaspve.com)

## The problem it solves

- Dense Proxmox tables, where storage and network relationships are hard to see.
- The risk of not booting after a kernel update.
- Opening SSH and forwarding a port just to get into a VM.

## What Atlas does

- **Guided storage and network operations**, with operation preview and rollback awareness.
- **Safe updates:** every update's dependencies, effects and changelog, shown up front.
- **SSH-free VM access:** in-VM terminal, file browser and metrics, with no SSH and no open port.
- **VMs and containers (LXC):** wizards for the common setups.
- **Backups and rollback:** a snapshot is taken before changes.
- **Live monitoring** of hosts, VMs and services.

## Why local and auditable

Atlas runs on your Proxmox host. Nothing connects in from outside, and the product works without an internet connection. Your VM, storage and network content is never sent to Atlas servers. Critical or privilege raising actions are written to an audit log: who, what, when, result.

## Frequently asked questions

### Is Atlas open source?

The agent that runs with root privileges on the server is open under AGPL, so what it does can be read and audited. The interface and product layer are offered under a commercial license, a deliberate choice that keeps Atlas funded and maintained.

### Can Atlas run offline?

Yes. Atlas runs offline and continues to operate locally on the Proxmox host. The internet is used only to fetch updates and the catalog. Without it, the installed version keeps working fully.

### Does Proxmox data pass through Atlas servers?

No. The Atlas management layer runs inside your own infrastructure. VM, storage and network content is not sent to Atlas servers.

### What happens if I do not renew updates?

Nothing gets locked. The installed local version keeps working. Only new features, security patches and compatibility updates for new Proxmox releases stop. When renewal is enabled again, update access returns.

### Who did what, is it auditable?

Critical or privilege raising actions, such as terminating a process, changing priority, or destructive storage and network operations, are written to an audit log with who, what, when and result.

### Do my Proxmox users and roles still apply?

Yes. Atlas does not build a parallel permission system. It mirrors Proxmox's own user, role, group and API token model. Proxmox decides who can see and do what, and Atlas follows it.

### Is this a subscription, or am I buying the license?

You are buying, not renting. The version you paid for runs indefinitely. If you do not renew, that version keeps running. Annual renewal covers new versions and update access.

## Links

- Website: [atlaspve.com](https://atlaspve.com)
- Live demo: [demo.atlaspve.com](https://demo.atlaspve.com)
- Account portal: [portal.atlaspve.com](https://portal.atlaspve.com)
