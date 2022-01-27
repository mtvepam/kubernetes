Hello Alexey!
To save your time here is a Canary deployment result:
![](17.jpg)
The following text represents the same in more details  :)
Kind regards
Tatiana

### ConfigMap & Secrets
Try connect to pod with curl (curl pod_ip_address). What happens?
From you PC
![](1.jpg)
From minikube (minikube ssh)
![](2.jpg)
From another pod (kubectl exec -it $(kubectl get pod |awk '{print $1}'|grep web-|head -n1) bash)
![](3.jpg)

### Create service (ClusterIP)
Try connect to service (curl service_ip_address). What happens?
From you PC
![](4.jpg)
![](5.jpg)
From minikube (minikube ssh) (run the command several times)
![](6.jpg)
From another pod (kubectl exec -it $(kubectl get pod |awk '{print $1}'|grep web-|head -n1) bash) (run the command several times)
![](7.jpg)

###NodePort
Checking the availability of the NodePort service type
![](8.jpg)

### DNS
Compare the IP address of the DNS server in the pod and the DNS service of the Kubernetes cluster.
![](9.jpg)
Inside the pod run nslookup to normal clusterip and headless. Compare the results.You will need to create pod with dnsutils.
![](10.jpg)

### Ingress
Let's see what the ingress controller creates for us
![](11.jpg)
![](12.jpg)

### HOMEWORK
In Minikube in namespace kube-system, there are many different pods running. Your task is to figure out who creates them, and who makes sure they are running (restores them after deletion).
![](13.jpg)

Implement Canary deployment of an application via Ingress. Traffic to canary deployment should be redirected if you add "canary:always" in the header, otherwise it should go to regular deployment. Set to redirect a percentage of traffic to canary deployment.
![](14.jpg)
![](15.jpg)
![](16.jpg)
![](17.jpg)