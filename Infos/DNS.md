# DNS

## Nützliche PowerShell-Befehle für DNS

### 1. DNS-Namen auflösen
```powershell
Resolve-DNSName -Name server1
```
Dieser Befehl wird verwendet, um den DNS-Namen `server1` aufzulösen. Er zeigt detaillierte Informationen wie IP-Adressen und DNS-Einträge an. Ideal, um die DNS-Konfiguration zu überprüfen. Die PowerShell Variante von ** nslookup **.

---

### 2. DNS-Client-Cache leeren
```powershell
Clear-DnsClientCache
```
Mit diesem Befehl wird der DNS-Cache des lokalen Clients geleert. Dies ist nützlich, wenn Änderungen an DNS-Einträgen vorgenommen wurden und der Cache veraltete Informationen enthält. Die PowerShell Variante von ** ipconfig /flushdns **

---

### 3. DNS-Client-Cache anzeigen
```powershell
Get-DnsClientCache
```
Dieser Befehl zeigt den aktuellen DNS-Cache des Clients an. Er ist hilfreich, um zu überprüfen, welche DNS-Einträge zwischengespeichert wurden. Die PowerShell Variante von  ** ipcpnfig /displaydns ** . 

---
### 4. DNS-Client bei DNS Server registrieren 
```powershell
Register-DnsClient
```
Dieses cmdlet registriert den DNS Client bei seinem DNS Server. Sodass der Eintrag des Clients beim DNS Server aktualisiert werden bzw erstmal registriert wurden. Die PowerShell Variante von  ** ipconfig /registernds **.
---

> **Hinweis für die Schulung:** Diese Befehle sind besonders nützlich, um DNS-Probleme zu diagnostizieren und zu beheben. Besondere Befehle wie zb Clear-DnsClientCache benötigen am client Admin Rechte