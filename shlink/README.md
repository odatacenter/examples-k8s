# shlink deploy example

* Change the [env credentials](./01-secret-env.yml)
* Change the ingresses of [shlink](./06-ingress-shlink.yml) and [webclient](./07-ingress-shlink-webclient.yml) URLs
* Apply each manifest in order, first shlink (wait db to deploy shlink), then webclient after key generate 
* Generate the API key with kubectl exec:
```
k exec -it (shlink pod) -- shlink api-key:generate
```
* Modify the apikey env of [webclient deployment](./05-deploy-shlink-webclient.yml)
* Apply the webclient manifests
