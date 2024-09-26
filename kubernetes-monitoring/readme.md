## Установка prometheus operator

$ kubectl create ns monitoring
$ helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
$ helm repo update

$ helm install prometheus-operator prometheus-community/kube-prometheus-stack --set rbacEnable=true --namespace=monitoring 

## Установка nginx ingress controller с поддержкой prometheus метрик

Необходимо установить новый деплоймент, в котором поднимается под с Nginx и nginx-exporter:
$ kubectl apply -f nginx-cm.yaml -f deployment.yaml -n monitoring

Добавим сервис:
$ kubectl apply -f service.yaml -n monitoring

Теперь можно запустить ServiceMonitor:
$ kubectl apply -f service-monitor.yaml -n monitoring