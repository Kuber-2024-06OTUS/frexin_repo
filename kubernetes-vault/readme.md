Установка нужных ресурсов из helm:

helm repo add hashicorp https://helm.releases.hashicorp.com
helm install consul hashicorp/consul --set server.replicas=3 --set global.name=consul --create-namespace -n consul
helm install vault hashicorp/vault --create-namespace -n vault --set ha.enabled=true 

Добавление нужной роли:

vault write auth/kubernetes/role/otus \
     bound_service_account_names=vault \
     bound_service_account_namespaces=vault \
     policies=default,app-policy

Установка CRD:

helm repo add external-secrets https://charts.external-secrets.io
helm install external-secrets external-secrets/external-secrets -n vault

