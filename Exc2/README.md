0) Запускаем minikube
minikube start
1) Создаем нейм спасе 
kubectl create namespace sprint6
2) Создаем развертыш
kubectl create -f scaleapp-deployment.yml
3) Запускаем сервис
kubectl create -f scaleapp-service.yaml
4) Устанавливаем контекс на созданный неймспасе 
kubectl config set-context --current --namespace=sprint6
4) прокидываем порт 
kubectl port-forward service/service-scaleapp 7080:8081
5) открываем страницу в бразузере
http://localhost:7080/
http://localhost:7080/metrics
6) Применяем hpa
kubectl apply -f hpa.yaml
kubectl get hpa
