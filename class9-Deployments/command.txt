1: kubectl create ns facebook
2: kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class9-Deployments/deployments/1-deployment-facebook.yaml

open 3 putty window

first putty window --> watch -n 1 kubectl describe deploy -n facebook
second putty window --> watch -n 1 kubectl get all -n facebook
third putty window --> you run al the below commands

kubectl rollout status deployment/nginx -n facebook
kubectl scale deployment/nginx --replicas=12 -n facebook --> to increase your replicas
kubectl edit deployment.apps/nginx -n facebook --> go and increase replicas count and save >--- then immedietly run the below command
kubectl rollout status deployment/nginx -n facebook
kubectl edit deploy/nginx -n facebook
kubectl apply -f 1-deployment-facebook.yaml -n facebook
kubectl rollout status deployment/nginx -n facebook

change below nginx version and save it

nginx:1.20-perl

kubectl rollout status deployment/nginx -n facebook

change below nginx version and save it

nginx:1.26.0

kubectl rollout status deployment/nginx -n facebook

change below nginx version and save it

nginx:1.25.5

kubectl rollout history deploy/nginx -n facebook

kubectl rollout undo deployment nginx --to-revision=1 -n facebook --> from 3rd version to first version we can go........

to see the status now --> kubectl rollout status deploy/nginx -n facebook


-------------------------------------------------------------------------------------------------------------------------------------------------

kubectl apply -f https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class9-Deployments/deployments/2-deployment-twitter.yml


kubectl get all -n facebook -o wide

kubectl describe deploy

kubectl get pod,service,replicaset,deploy -n facebook -o wide

to understand please delete one pod (before delete in another master ssh window keep run the watch -n 1 kubectl get all -n facebook -o wide command)

kubectl delete pod/nginx-74fcc59689-kn5j2 -n facebook

then 

run the below command again
kubectl get pod,service,replicaset,deploy -n facebook -o wide

rolling update --> https://raw.githubusercontent.com/cloudnloud/Kubernetes_Admin_Training/main/class9-Deployments/deployments/commands.txt
