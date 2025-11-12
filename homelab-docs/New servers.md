# Current 
- R5 4500
- gtx 1060
- 32GB
- 256 NVME boot
- 4 4TB
---
# Home server
- [ ] i5 13400
- [ ] 32GB
- [ ] 256 NVME boot
- [ ] 3 1TB SATA SSD
- [ ] 3 8TB

https://uk.pcpartpicker.com/list/LMnzQd
## Storage
- SSDs and parity HDD on mobo
- ZFS SSD
- MergerFS + SnapRAID cold storage
- MergerFS for ZFS + MergerFS
- Some sort of script to automatically move files last used 7 days or more ago or move the last used files if the ssd capacity exceeds a certain threshold
	- obsidian notes left alone
	- vaultwarden left alone
## Backup
- Restic
- Daily backup of combined MergerFS 
---
# Backup server
- [ ] Intel Core 300
- [ ] 16GB
- [ ] 256 NVME boot
- [ ] 3 8TB
---
# Networking?
- 2.5Gig (vm has 2.5 down)
- 10Gig to servers? (would be pretty sick)
---
# K3S cluster?
