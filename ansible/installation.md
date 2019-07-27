# Installtaion
### Installtion options: OS package maanger or PIP
```
sudo yum install -y ansible
```


### Configuration

configuration file - **/etc/ansible/ansible.cfg**

inventory file - **/etc/ansible/hots**

Empty the existing file 
```echo “ “ > /etc/ansible/hosts```

Create a static inventory:
``` vim /etc/ansible/hosts```

>[server]\n
>192.168.56.111
>[nodes]
>192.168.56.112
>192.168.56.113

### Syntax to execute ad-hoc command
```ansible <host-pattern> [options]```

```ansible <host-pattern> -m modulename```        # To execute an ansible module

```ansible <host-pattern> -a "linux_command"```   # To execute a linux command
