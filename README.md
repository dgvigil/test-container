TEST POD/CONTAINER
---------

This is a simple test with a scratch container, alpine based container, a go
app, and Kubernetes pod.


This is build with the following:

```
$ GOOS=linx go build -o read-simple-file main.go
$ docker build -t $YourRegistry/scratch-test:v1 -t $YourRegistry/scratch-test:init .
$ docker push $YourRegistry/scratch-test:v1
$ docker push $YourRegistry/scratch-test:init
$ kubectl apply -f pod.yaml
$ kubectl describe po test-pd
$ kubectl logs test-pd test-container-01
```
