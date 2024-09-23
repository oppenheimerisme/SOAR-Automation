# Automated Compliance Checks


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Basic login check for compliance

### Python (Basic Compliance Check Example)

```cpp

import os

def check_password_policy():
    with open('/etc/login.defs', 'r') as file:
        for line in file:
            if "PASS_MAX_DAYS" in line:
                print(line)

check_password_policy()

```

### PowerShell

```cpp

Get-ItemProperty -Path 'HKLM:\SYSTEM\CurrentControlSet\Services\Netlogon\Parameters' -Name 'PasswordExpiryWarning'

```
