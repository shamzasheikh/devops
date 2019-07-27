#### The deafult location of Ansible’s inventory is /etc/ansible/hosts. A different inventory file can be specified using the -i <path> option on the command line. <br/>
There are 2 types of inventory: <br/>
1. Static
2. Dynamic (hosts spinning up and shutting down in response to business demand)<br/>

> A host can be in multiple groups <br/>
> Groups can be nested <br/>

For the Hosts those run on non-standard SSH ports, put the port number after the hostname with a colon<br/>
```
...
  hosts:
    jumper:
      ansible_port: 5555
      ansible_host: 192.0.2.50
 
 ```
      
Also the connection type and user on a per host basis can be selected:<br/>
```
[targets]

localhost              ansible_connection=local
other1.example.com     ansible_connection=ssh        ansible_user=mpdehaan
other2.example.com     ansible_connection=ssh        ansible_user=mdehaan
```

#### Assigning a variable to one machine: host variables
```
atlanta:
  host1:
    http_port: 80
    maxRequestsPerChild: 808
  host2:
    http_port: 303
    maxRequestsPerChild: 909
 ```
 
 #### Assigning a variable to many machines: group variables
```
atlanta:
  hosts:
    host1:
    host2:
  vars:
    ntp_server: ntp.atlanta.example.com
    proxy: proxy.atlanta.example.com
 ```
 
 #### Deafult Groups
 There are two default groups: `all` and `ungrouped`. all contains every host. ungrouped contains all hosts that don’t have another group aside from all. Every host will always belong to at least 2 groups. Though all and ungrouped are always present, they can be implicit and not appear in group listingslike group_names
 
#### Organizing host and group variables
Though Variables are stored in the main inventory file, storing separate host and group variables files helps to track variable values more easily.

Host and group variables can be stored in individual files relative to the inventory file (not directory, it is always the file).

#### The group_vars/ and host_vars/ directories can exist in the playbook directory OR the inventory directory. If both paths exist, variables in the playbook directory will override variables set in the inventory directory.<br/>

## Dynamic Inventory 

For any fluctuation in inventory needs to be tracked from multiple sources like cloud providers, LDAP, Cobbler, and/or enterprise CMDB systems. Ansible supports two ways to connect with external inventory: 
`Inventory Plugins` and `Inventory scripts`




