---
title: Certificate
---

#### Certifikat ISS express
From <https://gist.github.com/camieleggermont/5b2971a96e80a658863106b21c479988> 

This powershell script generates a new certificate, removes the old certificate assignments from the IISExpress ssl ports and adds the newly generated one. The certificate is also copied over to the Trusted Root Certificate Authorities.

```ps1
$cert = New-SelfSignedCertificate -DnsName "localhost", "localhost" -CertStoreLocation "cert:\LocalMachine\My" -NotAfter (Get-Date).AddYears(5)
$thumb = $cert.GetCertHashString()
For ($i=44300; $i -le 44399; $i++) {
    netsh http delete sslcert ipport=0.0.0.0:$i
}
For ($i=44300; $i -le 44399; $i++) {
    netsh http add sslcert ipport=0.0.0.0:$i certhash=$thumb appid=`{214124cd-d05b-4309-9af9-9caa44b2b74a`}
}
$StoreScope = 'LocalMachine'
$StoreName = 'root'
$Store = New-Object  -TypeName System.Security.Cryptography.X509Certificates.X509Store  -ArgumentList $StoreName, $StoreScope
$Store.Open([System.Security.Cryptography.X509Certificates.OpenFlags]::ReadWrite)
$Store.Add($cert)
$Store.Close()
```