
kubectl get svc,pods,deployments -n chaos-mesh


kubectl port-forward -n chaos-mesh svc/chaos-dashboard 9090:2333 9091:2334

## Create token

 kubectl apply -f 3_pod_kill.yaml

 kubectl create token account-cluster-manager-fcjds

 # Create chaos



 kubectl get deployments,pod,svc -n chaos-sandbox --show-labels
 
 kubectl apply -f 3_pod_kill.yaml

 kubectl get -n chaos-sandbox po -w

 kubectl delete schedule pod-kill-example -n chaos-mesh\n
