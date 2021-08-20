##Create PersistentVolume y PersistentVolumeClaim

kubectl apply -f pvc-mysql-wp.yaml                                                                                                                                  

persistentvolumeclaim/mysql-pv-claim created
persistentvolumeclaim/wp-pv-claim created 

## Verify

kubectl get pv 

## Create password for MySQL database

kubectl apply -f secret.yaml

secret/mysql-pass created

## Verify

kubectl get secret

## Deploy MySQL Instance

kubectl apply -f mysql-deployment.yaml

service/wordpress-mysql unchanged
deployment.apps/wordpress-mysql created

## Verify

kubectl get pod

## Deploy Wordpress /var/www/html

kubectl apply -f wordpress-deployment.yaml 

service/wordpress created
deployment.apps/wordpress created

## Verify

kubectl get pod

## Check if all services are running correctly

kubectl get svc

## Access using the External-IP output from the above command

eg: http://172.104.37.236

## For Admin Panel 

eg: http://172.104.37.236/wp-admin



