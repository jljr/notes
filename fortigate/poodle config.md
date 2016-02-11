**Fortigate - Poodle Lockdown Config**


```
config vpn ssl settings
set tlsv1-0 disable
end
```

```
config system global
set admin-https-ssl-versions tlsv1-1 tlsv1-2
end
```

```
config system global  
set strong-crypto enable  
end 
```

```
config vpn ssl settings
set sslv3 disable  (enabled per default)
end
```