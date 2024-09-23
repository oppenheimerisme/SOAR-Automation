# Running Incident Response Playbooks


## Task

* Below is the Python and PowerShell script to automate the SOAR tasks
* Replace the "ips" with actual IPS
* Write the Incident reponse in a log file

### Python (Sample Playbook Flow)

```cpp

def run_playbook():
    suspicious_ips = ["192.168.1.100", "10.10.10.10"]
    for ip in suspicious_ips:
        block_ip(ip)
        log_event(f"Blocked IP {ip}")

def block_ip(ip):
    # Assuming 'iptables' for firewall
    command = f"iptables -A INPUT -s {ip} -j DROP"
    os.system(command)

def log_event(event):
    with open("incident_log.txt", "a") as log_file:
        log_file.write(event + "\n")

run_playbook()

```

### PowerShell

```cpp

$suspiciousIPs = @("192.168.1.100", "10.10.10.10")
foreach ($ip in $suspiciousIPs) {
    New-NetFirewallRule -DisplayName "Block $ip" -Direction Inbound -Action Block -RemoteAddress $ip
    Add-Content -Path "C:\incident_log.txt" -Value "Blocked IP $ip"
}

```
