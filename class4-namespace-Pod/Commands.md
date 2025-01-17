`````
kubectl get ns
```````
`````
kubectl get all -n default
`````
`````
kubectl get all -n kube-system
`````
`````
kubectl get all -n kube-system -o wide
`````

1. create name space

`````
kubectl create ns <namespace name>
`````
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/namespace/namespace.yaml
`````
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/namespace/namespace.yaml
`````
2. create pods...
`````
kubectl create ns twitter
`````
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/1-singlepod.yml
`````
`````
kubectl apply -f 1-singlepod.yml
`````
`````
kubectl get all -n twitter -l app=nginx
`````
`````
kubectl get all -n twitter -l version=v1
`````
`````
kubectl exec -it pod/webserver bash -n twitter
`````

now you need to understand that lablels will help you to create exact report and find the particular resources
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/1-singlepod.yml
`````

**************************************************************************************************************************************
`````
kubectl create ns facebook
`````
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/2-multipods.yml
`````
`````
kubectl get all -n facebook -l app=httpd
`````

`````
kubectl describe pod/multicontainer-pods -n facebook
`````
`````
kubectl exec -it pod/multicontainer-pods bash -n facebook
`````
`````
kubectl exec -it pod/multicontainer-pods bash -n facebook -c web
`````
`````
kubectl exec -it pod/multicontainer-pods bash -n facebook -c db
`````
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/2-multipods.yml
`````
************************************************************************************************************************************
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/2.1-duplicate-port-multipod.yaml
`````
`````
kubectl apply -f 2.1-duplicate-port-multipod.yaml
`````
same port it wont work ---
`````
kubectl get all -n facebook -l app=httpd
`````
`````
kubectl describe pod/multicontainer-pods -n facebook
`````
in this only one container will run another one will give you error
`````
kubectl logs pod/multicontainer-pods -n facebook -c httpd2
`````
`````
kubectl logs pod/multicontainer-pods -n twitter -c httpd1
`````
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/2.1-duplicate-port-multipod.yaml
`````
***********************************************************************************************************************************
`````
kubectl create ns twitter
`````
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/3-storage.yml
`````
`````
kubectl apply -f 3-storage.yml
`````
`````
kubectl get pods -n twitter -o wide
`````
`````
kubectl describe pod/database -n twitter
`````

check the directory has been created to that node

ls -ltrh /var/lib/postgres
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/3-storage.yml
`````
****************************************************************************************************************************************
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/4-multistorage.yml
`````
`````
kubectl get pods -n facebook -o wide
`````
`````
kubectl get all -n facebook -o wide
`````
`````
kubectl describe pod/db -n facebook
`````
`````
kubectl exec -it pod/db bash -n facebook -c web
`````
`````
kubectl exec -it pod/db bash -n facebook -c db
`````

ls -ltrh /var/www/html/
ls -ltrh /var/lib/postgres
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/4-multistorage.yml
`````
***************************************************************************************************************************************
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/5-full.yaml
`````
`````
kubectl get pods -n twitter -o wide
`````
`````
kubectl get all -n twitter -o wide
`````
`````
kubectl describe pod/webserver -n twitter
`````
`````
kubectl exec -it pod/webserver bash -n twitter -c web
`````
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/5-full.yaml
`````
***************************************************************************************************************************************
find out the below yaml file is deployed to which name space
`````
kubectl apply -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/6-example.yml -n rangarajbk
`````
`````
kubectl create ns rangarajbk
`````
`````
kubectl get all -n rangarajbk
`````
`````
kubectl get pod/first-pod -n rangarajbk
`````
`````
kubectl describe pod first-pod -n rangarajbk
`````
`````
kubectl delete -f https://raw.githubusercontent.com/rangarajbk/Kubernetes_Admin_Training/main/class4-namespace-Pod/pod/6-example.yml -n rangarajbk
`````
********************************************************************************************
`````
kubectl get ns
`````
`````
kubectl delete ns <namespace>
`````
