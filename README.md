# Unified hosts file with base extensions

#### AsusWRT and Asuswrt-Merlin
```bash
# Use the below command to get the hosts

wget -O /etc/hosts https://raw.githubusercontent.com/bushub/hosts/master/hosts

rm /jffs/configs/hosts

cp /etc/hosts /jffs/configs/hosts

# Flush DNS cache

killall -SIGHUP dnsmasq
```

#### Mac OS
```bash
# Use the below command to get the hosts

sudo mv /etc/hosts /etc/hosts.backup

sudo wget -O /etc/hosts https://raw.githubusercontent.com/bushub/hosts/master/hosts

# Flush DNS cache

sudo dscacheutil -flushcache

sudo killall -HUP mDNSResponder
```

#### Unix and Linux
```bash
# Use the below command to get the hosts

mv /etc/hosts /etc/hosts.backup

wget -O /etc/hosts https://raw.githubusercontent.com/bushub/hosts/master/hosts

# Flush DNS cache

systemctl restart dnsmasq

systemctl restart nscd
```

#### Windows
```
Windows PowerShell (Admin)
```
```powershell
# Use the below command to get the hosts

mv "C:\Windows\System32\drivers\etc\hosts" "C:\Windows\System32\drivers\etc\hosts.backup"

[Net.ServicePointManager]::SecurityProtocol = "tls13, tls12, tls11, tls"

Invoke-WebRequest -OutFile "C:\Windows\System32\drivers\etc\hosts" -Uri "https://raw.githubusercontent.com/bushub/hosts/master/hosts"

# Flush DNS cache

ipconfig /flushdns
```

