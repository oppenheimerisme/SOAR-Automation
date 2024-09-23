# File Hash Lookup


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Replace the "api_key" with your own key
* URL is the url of the open reputation check url (abuseipdb, VirusTotal, etc.)

### Python

```cpp

import requests

def check_file_hash(hash_value):
    api_key = "YOUR_VIRUSTOTAL_API_KEY"
    url = f"https://www.virustotal.com/vtapi/v2/file/report?apikey={api_key}&resource={hash_value}"
    response = requests.get(url)
    return response.json()

hash_value = "HASH_TO_CHECK"
result = check_file_hash(hash_value)
print(result)

```

### PowerShell

```cpp

$apiKey = "YOUR_VIRUSTOTAL_API_KEY"
$hashValue = "HASH_TO_CHECK"
$response = Invoke-RestMethod -Uri "https://www.virustotal.com/vtapi/v2/file/report?apikey=$apiKey&resource=$hashValue"
$response

```
