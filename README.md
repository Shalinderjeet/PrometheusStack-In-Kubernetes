Setup Prometheus Monitoring Stack in Kubernetes minikube cluster

Description:- Deploy Prometheus in local Kubernetes cluster using a Helm chart.

Different ways:-a. Creating all config files of Prometheus, Alert manager and Grafana etc by yourself then execute them in the right order         (Inefficient/cumbersome)
 b. Using an Operator (Manager of all promethues components)
 c. use Helm Chart to deploy the Operator (Helm will do the initial setup and Operator will manage the running setup)
                 
$helm install promethues stable/prometheus-operator

$kubectl get pod

$kubectl get all

2 stateful sets- a) Prometheus Server b) Alert Manager
3 Deployments- a) Prometheus Operator b) Grafana c) Kube state metrics (dependency of this Helm chart, scrapes the k8s components)
1 DaemonSet- Node Exportee DaemonSet (runs on all worker nodes, translates worker nodes metrics to prometheus metrics)


$kubectl logs grafanaone -c grafana
Its listening on port 3000


//Access Grafana UI
$kubectl port-forward deployment/prometheus-grafana 3000

default username-admin
default password prom-operator

//Access Prometheus UI
$kubectl port-forward promethuesPodname 9090
