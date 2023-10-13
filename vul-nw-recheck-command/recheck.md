# REcheck
## Requeriment
### updatedb
sudo nmap --script-updatedb
## Vuln check
### MS15-034 - CVE-2015-1635
nmap -p80 --script http-vuln-cve2015-1635
### SMBv1 enabled
nmap -p445 --script smb-protocols
### check mysql version
nmap -script mysql-info
### check mssql version
nmap -p 445 --script ms-sql-info
nmap -p 1433 --script ms-sql-info --script-args mssql.instance-port=1433
### OS detection

### NFS mount
```
namp script  
nfs-ls #List NFS exports and check permissions  
nfs-showmount #Like showmount -e  
nfs-statfs #Disk statistics and info from NFS share
```  
nmap -sV --script=nfs-showmount
### Mortbay / 

### nginx
```
port 80 common for nginx
```
nmap -sV -p80  
or  
nmap -sV  
### zimbra version check
reference : [zimbra-check](https://www.onyphe.io/docs/write-ups/diving-into-zimbra-cve-2022-27925-vulnerability-and-version-detection)  
curl -s --insecure -XGET 'https://your-ip/js/zimbraMail/share/model/ZmSettings.js' |grep -E 'CLIENT_RELEASE|CLIENT_VERSION'
