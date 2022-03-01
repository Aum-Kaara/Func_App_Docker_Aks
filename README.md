# Func_App_Docker_Aks
How to create Docker Image of Function App and run in AKS

### Prerequisite
 - VS Code
 - 
### Create Function App Project in VS Code

![image](https://user-images.githubusercontent.com/6815990/156152521-ed2de3b1-f07b-475c-bd2e-241d3b769f74.png)

![image](https://user-images.githubusercontent.com/6815990/156157757-cbd7c170-e8d0-4456-bef3-3a2d8dd735b7.png)

use command to generate Docker file 

```
func init --worker-runtime dotnet --docker --force
```

use below command to run Locally and test using postman

```
func start
```

![image](https://user-images.githubusercontent.com/6815990/156159071-5fa576d5-b17a-47a2-9362-f7aab9f3d826.png)

### Create Azure Continer Registry 

![image](https://user-images.githubusercontent.com/6815990/156159431-af9826ad-866d-4238-beb2-bfecac6a056a.png)

![image](https://user-images.githubusercontent.com/6815990/156159610-d58380a3-854c-460c-a9af-99f0ebaab0ce.png)

Enable Admin access so that we can login and push the images 

### Create Kubernetes Cluster

![image](https://user-images.githubusercontent.com/6815990/156160120-d7d033fe-c045-4493-ab99-4f6cbb910350.png)


### Create Image and push into ACR

Login into ACR
```
docker login faappsregistry.azurecr.io
```

Tag Image 

```
docker build --tag faappsregistry.azurecr.io/azurefunctionsimage:v1.0.0 .
```
