# Manage Volume
## Rename volume
```
scli --rename_volume --volume_id <ID> | --volume_name <NAME> --new_name <NAME>
```
## Take a snapshot
```
scli --snapshot_volume (--volume_id <ID> | --volume_name <NAME> | --volume_id_from_file <FILE> | --volume_name_from_file <FILE>) [--snapshot_name <NAME> | --snapshot_name_from_file <FILE>]
```
## Removing consistency group snapshots
```
scli --remove_consistency_group_snapshots --consistency_group_id <ID> [--i_am_sure]
```
## Remove volume
```
scli --remove_volume (--volume_id <ID> | --volume_name <NAME>) [Options] [--i_am_sure]
```
## Increasing a volume size
```
scli --modify_volume_capacity (--volume_id <ID> | --volume_name <NAME>) --size_gb <SIZE>
```
## Unmap volume
```
scli --unmap_volume_from_sdc (--volume_id <ID> | --volume_name <NAME>) (--sdc_id <ID> | --sdc_name <NAME> | --sdc_guid <GUID> | --sdc_ip <IP> | --all_sdcs) [--ignore_scsi_initiators] [--i_am_sure]
```

# Manage SDS
## Add SDS
```
scli --add_sds  --sds_ip <IP> --device_path <PATH> --protection_domain_name <NAME> --storage_pool_name <NAME> --sds_name <NAME>
```
## Rename SDS
```
scli --rename_sds (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) --new_name <NAME>
```
## Add IP to SDS
```
scli --add_sds_ip (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) --new_sds_ip <IP> [--sds_ip_role <ROLE>]
```
## Modify Role of IP on SDS
```
scli --modify_sds_ip_role (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) [--sds_ip_to_modify <IP>] --new_sds_ip_role <ROLE>
```
## Remove IP of SDS
```
scli --remove_sds_ip (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) --sds_ip_to_remove <IP>
```
## Modify SDS port
```
scli --modify_sds_port (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) --new_sds_port <PORT>
```
## Remove SDS
```
scli --remove_sds (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>)
```
## Aborting the removal of an SDS
```
scli --abort_remove_sds (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>)
```
## Manage SDS device
```
scli --add_sds_device (--sds_id <ID> |--sds_name <NAME> |--sds_ip <IP>)--device_path <PATH> [--device_name <NAME>] ((--storage_pool_name <NAME>) |--storage_pool_id <ID>) [--test_time] [Test Options]
```
## Remove device from SDS
```
scli --remove_sds_device (--device_id <ID> | ((--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) (--device_name <NAME> | --device_path <PATH>)))
```
## Aborting removal of a device from an SDS
```
scli --abort_remove_sds_device (--device_id <ID> | ((--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) (--device_name <NAME> | --device_path <PATH>)))
```
## Modifying the capacity of an SDS device
```
scli --modify_sds_device_capacity (--device_id <ID> | ((--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) (--device_name <NAME> | --device_path <PATH>))) --size_gb <SIZE>
```
## Clearing an SDS device error
```
scli --clear_sds_device_error (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) (--device_id <ID> | --device_name <NAME> | --device_path <PATH> | --clear_all)
```
## Updating an SDS device’s path
```
scli --update_device_original_path (--device_id <ID> | ((--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) (--device_name <NAME> | --device_path <PATH>)))
```
## Rename SDS device
```
scli --rename_device (--device_id <ID> | ((--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>) (--device_name <NAME> | --device_path <PATH>))) --new_name <NAME>
```
