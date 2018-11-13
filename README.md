## How it work's  
This zabbix templete discover all docker containers name and check if count of containers with some name less then CONTAINER_MIN_COUNT var. If actual count of containers is less then CONTAINER_MIN_COUNT for 2 minutes (2 last checks) then trigger with High value will send alert.  
## Getting Started  
1. Copy userparameter_docker.conf to /etc/zabbix/zabbix_agentd.d/  
`cp userparameter_docker.conf /etc/zabbix/zabbix_agentd.d/`  
2. Add lines from sudoers to /etc/sudoers  
```visudo
Defaults:zabbix !requiretty
zabbix ALL= (ALL) NOPASSWD: /usr/bin/docker ps*
```  
3. Import zabbix template
Zabbix main URL -> Configuration -> Templates -> Import  
4. Add template to Hosts  

TODO:  
- add variable with allowed containers name or name regex  
