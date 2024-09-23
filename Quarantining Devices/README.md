# Quarantining Devices


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Replace the "mac_address" with the actual one
* Cisco ISE url and Device group ID

### Python (Using Cisco ISE API)

```cpp

import requests

def quarantine_device(mac_address):
    url = "https://your-cisco-ise.com:9060/ers/config/endpoint"
    headers = {
        "Content-Type": "application/json",
        "Accept": "application/json",
        "Authorization": "Basic YOUR_AUTH_TOKEN"
    }
    data = {
        "ERSEndPoint": {
            "macAddress": mac_address,
            "groupId": "QUARANTINE_GROUP_ID"
        }
    }
    response = requests.put(url, headers=headers, json=data)
    return response.status_code

mac_address = "00:11:22:33:44:55"
quarantine_device(mac_address)


```

### PowerShell

```cpp

$macAddress = "00:11:22:33:44:55"
$headers = @{
    "Content-Type" = "application/json"
    "Authorization" = "Basic YOUR_AUTH_TOKEN"
}
$body = @{
    "ERSEndPoint" = @{
        "macAddress" = $macAddress
        "groupId" = "QUARANTINE_GROUP_ID"
    }
} | ConvertTo-Json
$response = Invoke-RestMethod -Method Put -Uri "https://your-cisco-ise.com:9060/ers/config/endpoint" -Headers $headers -Body $body
$response.StatusCode


```
