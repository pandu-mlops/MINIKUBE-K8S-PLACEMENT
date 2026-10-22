
start docker desktop

minikube is a container

go to working folder and open terminal

keep deployment , service,hpa(option) --yaml files in working folder

keep name of docker image in deployment file

keep service name as placement

minikube start --driver=docker

minikube status

minikube profile

then

kubectl commands use ===========================

kubectl get all

kubectl get all

kubectl get namespaces

kubectl create namespace <name>

-------------------------------------------------------------------------==================================

kubectl create namespace myai ---create name space indicates seperate infra for each project/env

kubectl get namespaces

kubectl create -f deployment.yaml   -------deployment of k8s

kubectl get all

docker inspect minikube

==========================================================

kubectl create -f service.yaml  ---- service of k8s

kubectl create -f hpa.yaml

=======================================================================================================

S C:\Users\abcde\OneDrive\Desktop\MLOPS-ASSIGNMENTS\placement\placement-minikube> minikube status                      
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

========================================================================================================

kubectl get all

=================================================================================

PS C:\Users\abcde\OneDrive\Desktop\MLOPS-ASSIGNMENTS\placement\placement-minikube> kubectl get all                      
NAME                             READY   STATUS    RESTARTS        AGE
pod/placement-7457c85b7f-pzv6d   1/1     Running   1 (33m ago)     89m
pod/placement-7457c85b7f-v8mtd   1/1     Running   1 (3m16s ago)   89m

NAME                 TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
service/kubernetes   ClusterIP      10.96.0.1       <none>        443/TCP        94m
service/placement    LoadBalancer   10.102.244.77   <pending>     80:32323/TCP   84m

NAME                        READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/placement   2/2     2            2           89m

NAME                                   DESIRED   CURRENT   READY   AGE
replicaset.apps/placement-7457c85b7f   2         2         2       89m

NAME                                            REFERENCE              TARGETS                                     MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/placement   Deployment/placement   cpu: <unknown>/70%, memory: <unknown>/80%   2         8         2          84m
PS C:\Users\abcde\OneDrive\Desktop\MLOPS-ASSIGNMENTS\placement\placement-minikube> 

==================================================================================================

minikube service placement ---tunnel create

http://127.0.0.1:51320

http://127.0.0.1:51320/predict   -- test at postman

minikube service placement --url


minikube addons enable metrics-server

================================================================================

PS C:\Users\abcde\OneDrive\Desktop\MLOPS-ASSIGNMENTS\placement\placement-minikube> kubectl get all           
NAME                             READY   STATUS    RESTARTS       AGE
pod/placement-7457c85b7f-pzv6d   1/1     Running   1 (37m ago)    93m
pod/placement-7457c85b7f-v8mtd   1/1     Running   1 (7m7s ago)   93m

NAME                 TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
service/kubernetes   ClusterIP      10.96.0.1       <none>        443/TCP        98m
service/placement    LoadBalancer   10.102.244.77   <pending>     80:32323/TCP   88m

NAME                        READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/placement   2/2     2            2           93m

NAME                                   DESIRED   CURRENT   READY   AGE
replicaset.apps/placement-7457c85b7f   2         2         2       93m

NAME                                            REFERENCE              TARGETS                        MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/placement   Deployment/placement   cpu: 0%/70%, memory: 66%/80%   2         8         2          87m
PS C:\Users\abcde\OneDrive\Desktop\MLOPS-ASSIGNMENTS\placement\placement-minikube> 

======================================================================================================================
