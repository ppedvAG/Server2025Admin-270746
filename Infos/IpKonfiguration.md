# IP Konfiguration

Konfigurieren der IP Adresse , SubnetzMaske und DNS Server über die PowerShell
Als erstes muss man den Index zu konfigurierenden Interfaces festellen über den Befehl
[Get-NetAdapter Doku](https://learn.microsoft.com/en-us/powershell/module/netadapter/get-netadapter?view=windowsserver2025-ps)
```powershell
Get-NetAdapter
```
Dort sollte man dann das richtige Interface auswählen da die Interface Index Nr im folgenden Befehel benötigt wird. In diesem Beispiel wird für das Interface mit der Index Nummer 4 die IP Adresse **192.168.10.3** mit einer Präfix von **24** gesetzt was einer Subnetzmaske von **255.255.255.0** entspricht. Es wäre hier auch möglich mit einem weiteren Parameter das Standardgateway anzugeben was in diesem Falle hier aber entfällt.

[New-NetIpaddress Doku](https://learn.microsoft.com/en-us/powershell/module/nettcpip/new-netipaddress?view=windowsserver2025-ps)
```powershell
New-NetIPAddress -InterfaceIndex 4 -IPAddress 192.168.10.3 -PrefixLength 24 
```
Anschließend muss lediglich noch dem DNS Client die Adresse des bevorzugten DNS Servers mitgeteilt werden. Auch wird wieder die InterfaceIndex Nummer verwendet. Ein zweiter DNS würde hier mit einem Komma angegeben hinter der ersten Adresse.

[Set-DnsClientServerAddress Doku](https://learn.microsoft.com/en-us/powershell/module/dnsclient/set-dnsclientserveraddress?view=windowsserver2025-ps)
```powershell
Set-DnsClientServerAddress -InterfaceIndex 4 -ServerAddresses 192.168.10.1
```
---