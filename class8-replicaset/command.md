Replica set
```````
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/1-singlereplica.yml
```````
```````
kubectl get all -n twitter
```````
```````
kubectl describe replicas -n twitter
```````
```````
kubectl get pod,service,replicaset -n twitter -o wide
```````

labels --> service -- selector , replica -- match ---> should be same
```````
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/1-singlereplica.yml
```````
**************************************************************************************************************************************
```````
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/2-singlepod-singlereplica.yml
```````
```````
kubectl get all -n facebook
```````
```````
kubectl describe replicas -n facebook
```````
```````
kubectl get pod,service,replicaset -n facebook -o wide
```````
labels --> service -- selector , replica -- match ---> should be same
```````
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/2-singlepod-singlereplica.yml
```````
**************************************************************************************************************************************
```````
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/3-multireplica.yaml
```````
```````
kubectl get all -n facebook
```````
```````
kubectl describe replicas -n facebook
```````
```````
kubectl get pod,service,replicaset -n facebook -o wide
```````
labels --> service -- selector , replica -- match ---> should be same
```````
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/3-multireplica.yaml
```````
********************************************************************************************************************************************
```````
kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/5-replica-nodeport.yml
```````
```````
kubectl get all
```````
```````
kubectl describe replicas
```````
```````
kubectl get pod,service,replicaset -n facebook -o wide
```````
labels --> service -- selector , replica -- match ---> should be same
```````
kubectl delete -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class8-replicaset/replicaset/5-replica-nodeport.yml
```````
