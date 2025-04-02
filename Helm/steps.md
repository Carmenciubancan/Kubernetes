#### Install stateful app MongoDB on managed K8s service in the cloud


* Deploy a managed K8s cluster on a cloud provider (digital ocean)

    * Download kubeconfig file
    * chmod 400 test-kubeconfig.yaml 
    * export KUBECONFIG=test.kubeconfig.yaml
    * brew install helm
    * helm repo add bitnami https://charts.bitnami.com/bitnami

* Deploy a replicated DB and configure its persistance data

    * helm search repo bitnami/mongodb
    * helm install mongodb --values helm-mongodb.yaml bitmani/mongodb

* Deploy mongoexpress UI 

    * one pod, one service 
    * create a k8s deployment (helm-mongoexpress.yaml)


* Make it accessible through the UI using ingress

    * helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
    * helm install nginx-ingress ingress-nginx/ingress-nginx --set controller.publishService.enabled=true
    * kubectl apply -f helm-ingress.yaml