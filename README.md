docker build -t sravanscker/spring-boot-localdb:1.0 .

docker tag sravanscker/spring-boot-localdb:1.0 . sravanscker/spring-boot-localdb:1.0 .

docker push sravanscker/spring-boot-localdb:1.0 .

kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

post http://localhost:30007/users
get http://localhost:30007/users
