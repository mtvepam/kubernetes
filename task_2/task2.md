### ConfigMap & Secrets
Try connect to pod with curl (curl pod_ip_address). What happens?
From you PC
!(1.jpg)
From minikube (minikube ssh)
!(2.jpg)
From another pod (kubectl exec -it $(kubectl get pod |awk '{print $1}'|grep web-|head -n1) bash)
!(3.jpg)