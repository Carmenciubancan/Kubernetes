# Deploy mongoDB and mongo express into a local K8s cluster ( Minikube )

Steps: 

1. install minikube on local
2. create a mongodb deployment + internal service
3. create secret file and store (encoded) DB credentials
4. create mongo-express deployment file
5. create configMap file and store DB URL 
6. apply configurations and have :
 - 2 deployments
 - 2 pods; mongodb & mongoexpress (running)
 - 2 services; interntal & external
 - 1 config map
 - 1 secret

__________________________________________

´$ brew install minikube´

´$ minikube start --driver docker´

´$ kubectl get all´ # lists all the components inside the cluster

´$ vim mongo-deployment.yaml´ #create deployment conf file

´$ vim mongo-secret.yaml´ # create secret file to store credentials

´$ echo -n 'username' | base64´
´$ echo -n 'password' | base64´ # encode credentials in base64

* store the encoded credentials into deployment config file

´$ kubectl apply -f [secret file name]´ 

´$ kubectl get secret´ #lists existing secrets

´$ kubectl apply -f [deployment file name]´ #applies the deployment configuration and creates it


´´

´´

´´

