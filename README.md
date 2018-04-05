# OAuth Proxy Experiments on OpenShift

## UPS with Oauth Proxy for Github Auth based on Org membership

Manual steps at this time.

Modify `dc_ups.yml` to set the following

* route where the proxy will be accesible from - `--redirect-url=<route>/oauth2/callback`
* github-org to restrict users to - `--github-org=myorg`
* client-id for Github OAuth app - `--client-id=<clientid>`
* client-secrete for Github OAuth app `--client-secret=<clientsecret>`

```
oc create -f dc_mysql..yml
oc create -f svc_mysql..yml
oc create -f dc_ups..yml
oc create -f svc_ups-proxy..yml
oc create -f route_ups..yml
```
