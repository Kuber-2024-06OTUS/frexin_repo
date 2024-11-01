Вначале установим argocd через helm:

helm pull oci://cr.yandex/yc-marketplace/yandex-cloud/argo/chart/argo-cd --version 7.3.11-2 --untar 
helm install -f custom-values.yaml --namespace homework  argo-cd ./argo-cd/ 

Получим из консоли после установки пароль администратора:
ZtuVXjLThpYRYbMM

Настроим port forwarding и залогинимся в веб-интерфейс.
Создадим оба приложения и проверим их работу.
Манифесты приложений и проекта лежат в папке manifests.