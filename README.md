Setup Prometheus Monitoring in Kubernetes

Description:- Deploy Prometheus in local Kubernetes cluster using a Helm chart.

Different ways:-a. Creating all config files of Prometheus, Alert manager and Grafana etc by yourself then execute them in the right order         (Inefficient/cumbersome)
 b. Using an Operator (Manager of all promethues components)
 c. use Helm Chart to deploy the Operator (Helm will do the initial setup and Operator will manage the running setup)
                 
