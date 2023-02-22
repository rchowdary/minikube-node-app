# apply the deployment using folder kube 
-   (all yaml files will be used from folder)
minikube kubectl -- apply -f kube
<!---
service/node-dockerapp created
deployment.apps/node-dockerapp unchanged
-->


minikube service node-dockerapp --url
<!---
http://192.168.49.2:31000
-->


minikube kubectl -- get pods

minikube kubectl -- get svc
<!---
NAME             TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
kubernetes       ClusterIP   10.96.0.1       <none>        443/TCP          14d
node-dockerapp   NodePort    10.110.174.75   <none>        8080:31000/TCP   8s
-->
minikube ip
<!---
192.168.49.2
-->
minikube dashboard


# cleanup
minikube kubectl -- delete deployment.apps/node-dockerapp
minikube kubectl -- delete service/node-dockerapp

minikube stop