## Overview Query
```
scli --query_all
```
## MDM cluster query
```
scli --query_cluster
```
## Restricted SDC mode query
```
scli --query_restricted_sdc_mode
```
## Protection Domain Query
```
scli --query_protection_domain (--protection_domain_id <ID> | --protection_domain_name <NAME>)
```
## Query a specific Fault Set
```
scli --query_fault_set (--fault_set_id <ID> | ((--protection_domain_id <ID> | --protection_domain_name <NAME>) --fault_set_name <NAME>))
```
## Query all Fault Sets in a Protection Domain
```
scli --query_all_fault_sets (--protection_domain_id <ID> | --protection_domain_name <NAME>)
```
## Storage Pool query
```
scli --query_storage_pool (((--protection_domain_id <ID> | --protection_domain_name <NAME>) --storage_pool_name <NAME>) | --storage_pool_id <ID>)
```
## Query SDS connectivity status
```
scli --query_sds_connectivity_status (--protection_domain_id <ID> | --protection_domain_name <NAME>)
```
## Query a specific SDS node
```
scli --query_sds (--sds_id <ID> | --sds_name <NAME> | --sds_ip <IP>)
```
## Query all SDS nodes
```
scli --query_all_sds
```
## Query a specific SDC node
```
scli --query_sdc --sdc_id <ID> | --SDC_name <NAME> | --sdc_guid <GUID> | --sdc_ip <IP>
```
## Volume query
```
scli --query_volume (--volume_id <ID> | --volume_name <NAME>)
```
## Volume tree query
```
scli --query_volume_tree (--volume_id <ID> | --volume_name <NAME>)
```
## All volumes query
```
scli --query_all_volumes [(((--protection_domain_id <ID> | --protection_domain_name <NAME>) --storage_pool_name <NAME>) | --storage_pool_id <ID>)]
```
## All device latency meters query
```
scli --query_all_device_latency_meters [(--protection_domain_id <ID> | --protection_domain_name <NAME>)]
```
## License query
```
scli --query_license
```
## Remote syslog query
```
scli --query_remote_syslog
```
