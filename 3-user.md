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
# Authenticating with the MDM
## Login
```
scli --login --username <NAME> [--password <PASSWORD>]
```
## Logoute
```
scli --logout
```

# Add & Modify User
## Add user
```
scli --add_user --username <NAME> --user_role <Monitor|Configure|Administrator>
```
## Delete user
```
scli --delete_user (--user_id <ID> | --username <NAME>)
```
## Modify User credentials
```
scli --modify_user (--user_id <ID> | --username <NAME>) --user_role <Monitor|Configure|Administrator>
```
## Display user
```
scli --query_users
```
## Display information for a user
```
scli --query_user (--user_id <ID> | --username <NAME>)
```
## Reset User Password
```
scli --reset_password (--user_id <ID> | --username <NAME>)
```
## Change password
```
scli --set_password [--old_password <OLD_PASSWORD>] [--new_password <NEW_PASSWORD>]
```
## Reset Admin password
```
scli --reset_admin
```


