# Prepare the MDM
## Setting up Primary MDM
```
scli --add_primary_mdm --primary_mdm_ip <IP> [--mdm_management_ip <IP>] [--accept_license]
```
## Setting up secondary MDM
```
scli --add_secondary_mdm –-secondary_mdm_ip <IP> [--secondary_mdm_port <PORT>]
```
## Add a Tie_breaker
```
scli --add_tb –-tb_ip <IP> [--tb_port <PORT>] [--force_clean][--i_am_sure]
```
## Active MDM cluster
```
scli --switch_to_cluster_mode
```
## Setting data obfuscation
```
scli --set_obfuscation_properties (--use_obfuscation | --dont_use_obfuscation)
```

# Adding capacity
## Add a Protection Domain
```
scli --add_protection_domain [--protection_domain_name <NAME>]
```
## Add Fault Set
```
scli --add_fault_set (--protection_domain_id <ID> | --protection_domain_name <NAME>) [--fault_set_name <NAME>]
```
## Add Storage Pool
```
scli --add_storage_pool (--protection_domain_id <ID> | --protection_domain_name <NAME>) [--storage_pool_name <NAME>] [--use_rmcache | --dont_use_rmcache] [--rmcache_write_handling_mode <passthrough/cached>]
```
## Modify Spare Policy
```
scli modify_spare_policy (((--protection_domain_id <ID> | --protection_domain_name <NAME>) --storage_pool_name <NAME>) | --storage_pool_id <ID>) --spare_percentage <PERCENT> [--i_am_sure]
```
## Setting a capacity alert threshold
```
scli --set_capacity_alerts_threshold --capacity_high_threshold <PERCENT> --capacity_critical_threshold <PERCENT>
```


# Creating & Mapping Volume
## Creating
```
scli --add_volume (((--protection_domain_id <ID> | --protection_domain_name <NAME>) --storage_pool_name <NAME>) | --storage_pool_id <ID>) --size_gb <SIZE> [--volume_name <NAME>] [Options] [Obfuscation Options] [Use RAM Read Cache Options]
```
Volume sau khi được tạo ra, volume sẽ không sử dụng được cho đến khi nó được map tới ít nhất 1 SDC.
Mặc định volume được tạo ra sử dụng volume caching và không sử dụng option obfuscated.

## Mapping 
```
scli --map_volume_to_sdc (--volume_id <ID> | --volume_name <NAME>) (--sdc_id <ID> | --sdc_name <NAME> | --sdc_guid <GUID> | --sdc_ip <IP>) [--allow_multi_map]
```
Option `--allow_multi_map` cho phép volume được map tới nhiều hơn 1 SDC.

## Detecting
Command detach volume `drv_dfg --rescan`. Đây không phải là CLI command mà là một thực thi được chạy trên máy chủ SDC.
```
/opt/emc/scaleio/sdc/bin/drv_cfg --rescan
```

