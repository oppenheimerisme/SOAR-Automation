# Phishing Investigation and Response


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Replace the "email.eml" with actual email path

### Python (Extracting Email Headers)

```cpp

import email
from email import policy
from email.parser import BytesParser

def extract_headers(file_path):
    with open(file_path, 'rb') as f:
        msg = BytesParser(policy=policy.default).parse(f)
    return msg.items()

headers = extract_headers('/path/to/email.eml')
print(headers)

```

### PowerShell

```cpp

$emailPath = "C:\Emails\phishing_email.eml"
$headers = Get-Content -Path $emailPath
$headers

```
