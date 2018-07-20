# Install
## Node Prepare
Install package require
```
apt install numactl libaio1 
```
Install package additional for MDM
```
apt install bash-completion python2.7
```
Install Java for Gateway Server only
```
apt-get install openjdk-8-jre binutils
```

## Install Gateway Server on ScaleIO-Master
Install Gateway
```
GATEWAY_ADMIN_PASSWORD=admin dpkg -i ScaleIO_2.0.1.4_Gateway_for_Linux_Download/emc-scaleio-gateway_2.0-14000.231_amd64.deb
```
**Prepare CSV File** to install full IM  
Go to `https://10.5.9.64` with user `admin` & password `admin`  
Go to packages tab --> Browse --> EMC lia,mdm,sdc,sds --> Open --> Upload --> Proceed to Install  
Browse --> Choose File CSV --> Upload installation CSV  
Enter new password for MDM & LIA --> Accept the term --> Click Install  
Go to monitor tab --> Start upload phase --> Start install phase --> Start configure phase --> Mark operation completed  

## Config SDC
Change file `/bin/emc/scaleio/scini_sync/driver_sync.conf`
```
repo_address = ftp://ftp.emc.com/
repo_user = QNzgdxXix
repo_password = Aw3wFAwAq3
module_sigcheck = 0
```
Restart service scini
```
service scini restart
```
## Enable Storage
Log in to the ScaleIO cluster
```
scli --login --username admin --password <MDM PASSWORD>
```
Add sds device
```
scli --add_sds_device --sds_ip 10.5.9.66 --protection_domain_name default --storage_pool_name default --device_path /dev/vdb
```
Create volume
```
scli --add_volume --protection_domain_name default --storage_pool_name default --size_gb 20 --volume_name volume1
```
Map volume to SDC
```
scli --map_volume_to_sdc --volume_name volume1 --sdc_ip 10.5.9.63
```
Review
```
scli --query_all
```
