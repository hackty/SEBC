```
[libdefaults]
default_realm = HACKTY.COM
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = arcfour-hmac
default_tkt_enctypes = arcfour-hmac
permitted_enctypes = arcfour-hmac
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
HACKTY.COM = {
kdc = ip-172-31-27-83.ec2.internal
admin_server = ip-172-31-27-83.ec2.internal
}
```
