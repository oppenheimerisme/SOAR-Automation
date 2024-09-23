# Disabling User Accounts (Active Directory)


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Replace the "server" with your own LDAP server
* Domain name, username and password are the inputs

### Python

```cpp

from ldap3 import Server, Connection, ALL

def disable_user_account(username):
    server = Server('ldap://your-domain.com', get_info=ALL)
    conn = Connection(server, 'cn=admin,dc=example,dc=com', 'password', auto_bind=True)
    conn.modify(f'cn={username},ou=users,dc=example,dc=com', {'userAccountControl': [(2, 514)]})

username = "john_doe"
disable_user_account(username)


```

### PowerShell

```cpp

Import-Module ActiveDirectory
Disable-ADAccount -Identity "john_doe"


```
