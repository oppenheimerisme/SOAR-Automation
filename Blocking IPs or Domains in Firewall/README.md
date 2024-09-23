# Blocking IPs or Domains in Firewall


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Change "ip" value to the IP/Domain that you want to block

### Python

```cpp

import os

def block_ip(ip_address):
    command = f"iptables -A INPUT -s {ip_address} -j DROP"
    os.system(command)
    
ip = "192.168.1.100"
block_ip(ip)

```

### PowerShell

```cpp

$ip = "192.168.1.100"
New-NetFirewallRule -DisplayName "Block IP $ip" -Direction Inbound -Action Block -RemoteAddress $ip

```
