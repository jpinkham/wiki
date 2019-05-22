### Find local certificates expiring in the next 30 days
```Get-ChildItem -Path cert: -Recurse -ExpiringInDays 30 | Format-List```

Example output:

```
Subject      : CN=ABC123
Issuer       : CN=Apple iPhone Device CA, OU=Apple iPhone, O=Apple Inc., C=US
Thumbprint   : <hex string>
FriendlyName : APNS certificate Direct            
NotBefore    : 5/24/2018 4:24:55 PM                 
NotAfter     : 5/24/2019 4:29:55 PM
Extensions   : {System.Security.Cryptography.Oid, System.Security.Cryptography.Oid, System.Security.Cryptography.Oid, System.Security.Cryptography.Oid...}   
```



