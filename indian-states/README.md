
* made changes to 
  * `pom.xml` - SpringBoot  - Java - Docker image - Maven plugin
  * `mydeployment.yaml` - image
  * `skaffold.yaml` - image

* #### Skaffold commands (ctrl + c to exit)

```
skaffold diagnose
skaffold build
skaffold dev

kubectl get nodes
kubectl get pods
kubectl get svc
kubectl describe pod <pod-name>

curl localhost:8080/states
curl -X GET "localhost:8080/state?name=Karnataka"
```


<br>

---

# About Project
This is a simple Spring Boot application which, when accessed via /states or /state?name=statename REST endpoint show all or specific Indian states and their capitals. This application uses an in-memory H2 database that inserts rows at the start of the application

# About Skaffold
> Skaffold handles the workflow for building, pushing and deploying your application.

# How to start project locally
 * Install skaffold
    `brew install skaffold`
 * Install Docker Desktop for [Mac](https://www.docker.com/products/docker-desktop) for running kubernetes locally
 * Install kubectl (Optional for Docker Desktop)
 `brew install kubectl`

`git clone https://github.com/yrashish/indian-states`

`skaffold dev`

# Demo
[![Demo](https://img.youtube.com/vi/KR8DqxaOGBw/2.jpg)](https://www.youtube.com/watch?v=KR8DqxaOGBw)



