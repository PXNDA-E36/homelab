# LXC
```
sudo groupadd -g 10000 nas_shares

sudo adduser user nas_shares 
```
# Proxmox

```
groupadd -g 110000 nas_shares

useradd nas -u 101000 -g 110000 -m -s /bin/bash

chown -R nas:nas_shares /pool_name/dataset_name

pct set container_id -mpX /pool_name/dataset_name,mp=/mnt/dataset
```
