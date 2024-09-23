#User Activity Review (Log Parsing)


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* USER is the username of user activity you want to perform analysis on

### Python

```cpp

import re

def check_user_activity(log_file, user):
    with open(log_file, 'r') as f:
        for line in f:
            if re.search(user, line):
                print(line)

log_file = '/var/log/auth.log'
user = 'john_doe'
check_user_activity(log_file, user)

```

### PowerShell

```cpp

$user = "john_doe"
$logfile = "C:\Logs\auth.log"
Select-String -Path $logfile -Pattern $user

```
