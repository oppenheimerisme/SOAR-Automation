# GeoIP Lookup


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Replace the "ip" with your own IP

### Python

```cpp

import requests

def get_geoip(ip):
    url = f"http://ip-api.com/json/{ip}"
    response = requests.get(url)
    return response.json()

ip = "8.8.8.8"
geoip_data = get_geoip(ip)
print(geoip_data)

```

### PowerShell

```cpp

$ip = "8.8.8.8"
$response = Invoke-RestMethod -Uri "http://ip-api.com/json/$ip"
$response

```
