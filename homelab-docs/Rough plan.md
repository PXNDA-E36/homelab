# Storage
- ZFS pool
- 2 datasets
	- Arr (mapped to all arr containers that need)
	- Immich
- Pass through drive harvested from hikvision nvr to frigate

> [!NOTE]
> Create ZFS Pool: Go to Datacenter > Storage > Add > ZFS, name your pool, and select the desired disks.
> Add Datasets: In the terminal, run zfs create poolname/datasetname for each dataset.
> Configure Storage: In Proxmox, go to Datacenter > Storage > Add > ZFS (Dataset), select the dataset, and set usage (VMs, containers, etc.).
# VLANS
- Main
	- 192.168.0.0/24
	- Broadcasted by APs
	- Can access everything
- Guest 
	- 192.168.1.0/24
	- Broadcasted by APs
	- Can only access internet
- Server Default
	- 10.0.0.0/24
	- Proxmox
	- Can only access internet
- Services 3
	- 10.0.10.0/24
	- Dashboard can access HA and arr
	- Headscale can access HA
- Arr 4
	- 10.0.20.0/24
	- Can only access internet
- IoT 
	- 10.0.30.0/24
	- Can access only internet and jellyfin
- HA 
	- 10.0.40.0/24
	- Completely blocked off
- CCTV/Frigate
	- 10.0.50.0/24
	- Frigate can access HA

![[VLAN.canvas|VLAN]]
# Remote Access
- 443 and 80 exposed
- Mapped to nginx
- Only allow in from cloudflare servers 
# Potential Pi Stuff
- Home Assistant
- Frigate
# Potential Router Stuff
- OpenWRT
- Pi-Hole