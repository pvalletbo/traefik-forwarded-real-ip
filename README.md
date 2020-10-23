# Traefik X-Real_ip OverWriter Plugin

If Traefik is behind a load balancer, it won't be able to get the Real IP from the external client by checking
the remote IP address. 

This plugin solves this issue by overwriting the `X-Real-Ip` with an IP from the `X-Forwarded-For` header.
The real IP will be the first one that is not included in any of the CIDRs passed as the `ExcludedNets` parameter. 
The evaluation of the X-Forwarded-For IPs will go from the last to the first one.
