**Fortigate - Test IPSec VPN**

```
diagnose debug disable
diagnose vpn ike log-filter clear
diagnose vpn ike log-filter dst-addr4 X.X.X.X
diagnose debug app ike 255
diagnose debug enable

diagnose debug disable
```