# IP Address & Domain Reputation Check


## Task

* Below is the Python script to automate the SOAR tasks
* Replace the "api_key" with your own key
* URL is the url of the open reputation check url (abuseipdb, VirusTotal, etc.)

### Python

```cpp

import requests

def check_ip_reputation(ip_address):
    api_key = "YOUR_API_KEY"
    url = f"https://api.abuseipdb.com/api/v2/check?ipAddress={ip_address}"
    headers = {
        "Key": api_key,
        "Accept": "application/json"
    }
    response = requests.get(url, headers=headers)
    return response.json()

ip = "8.8.8.8"
result = check_ip_reputation(ip)
print(result)

```

### PowerShell

```cpp

$apiKey = "YOUR_API_KEY"
$ip = "8.8.8.8"
$headers = @{
    "Key" = $apiKey
    "Accept" = "application/json"
}
$response = Invoke-RestMethod -Uri "https://api.abuseipdb.com/api/v2/check?ipAddress=$ip" -Headers $headers
$response

```
