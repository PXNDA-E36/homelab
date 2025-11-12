# Proxmox setup
1. Download driver .run from NVIDIA
2. Setup LXC using wizard
3. Append following to /etc/pve/lxc/ID.conf
```
lxc.cgroup2.devices.allow: c 195:* rwm
lxc.cgroup2.devices.allow: c 236:* rwm
lxc.cgroup2.devices.allow: c 511:* rwm
lxc.mount.entry: /dev/nvidia0 dev/nvidia0 none bind,optional,create=file
lxc.mount.entry: /dev/nvidiactl dev/nvidiactl none bind,optional,create=file
lxc.mount.entry: /dev/nvidia-modeset dev/nvidia-modeset none bind,optional,create=file
lxc.mount.entry: /dev/nvidia-uvm dev/nvidia-uvm none bind,optional,create=file
lxc.mount.entry: /dev/nvidia-uvm-tools dev/nvidia-uvm-tools none bind,optional,create=file
lxc.mount.entry: /dev/nvidia-caps/nvidia-cap1 dev/nvidia-caps/nvidia-cap1 none bind,optional,create=file
lxc.mount.entry: /dev/nvidia-caps/nvidia-cap2 dev/nvidia-caps/nvidia-cap2 none bind,optional,create=file
```
4. Start lxc and push driver .run to /home/user
# LXC setup
1. Run driver .run with --no-kernel-modules
2. [[Docker install|Install docker]]
3. [[NVIDIA Container Toolkit install|Install NVIDIA toolkit]]
4. edit /etc/nvidia-container-runtime/config.toml and set no-cgroups = true