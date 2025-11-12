# Delete local-lvm and Resize local
1. Delete local-lvm manually from web interface
2. Run the following commands

```
lvremove /dev/pve/data
lvresize -l +100%FREE /dev/pve/root
resize2fs /dev/mapper/pve-root
```

3. Check to ensure your local storage partition is using all available space