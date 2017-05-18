
# Instructions

## Azure CLI 1.0

``` 
azure servicefabric cluster connect --connection-endpoint http://$SERVICE_FABRIC_CLUSTER:19080
azure servicefabric application package copy /mnt/c/tmp/HelloWorldApplication/ fabric:ImageStore HelloWorldApplicationType
azure servicefabric application type register HelloWorldApplication
azure servicefabric application create fabric:/HelloContainerApplication HelloWorldApplicationType 1.0.0
```

## Azure CLI 2.0

```
az sf cluster select --endpoint http://$SERVICE_FABRIC_CLUSTER:19080
az sf application upload --show-progress --path /mnt/c/tmp/HelloWorldApplication/
az sf application provision --application-type-build-path HelloWorldApplication
az sf application create --name fabric:/HelloWorldApplication --app-type HelloWorldApplicationType --version 1.0.0
```
