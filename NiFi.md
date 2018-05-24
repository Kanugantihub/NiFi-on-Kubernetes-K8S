# Apache NiFi on Kubernetes

## Install Kubernetes

* Install kubernetes using minikube

        brew install minikube
 
* Start minikube
 
        minikube start --memory=4096
               
* Mount folder to minikube, so that pods can have access to local storage
        
        minikube mount <src-dir>:/<dst-dir>

* Let K8s use local docker env

        eval $(minikube docker-env)
                                  
* Create default memory limits

        kubectl create -f memory-defaults.yaml
        
* Create Apache NiFi Deployment

        kubectl create -f nifi.yaml
        
* Create Apache NiFi Service

        kubectl create -f nifi-svc.yaml

* Run the following command to open Apache NiFi dashboard

        minikube service flow-4                