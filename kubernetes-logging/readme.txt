$ kubectl get node -o wide --show-labels

NAME                        STATUS   ROLES    AGE   VERSION   INTERNAL-IP   EXTERNAL-IP      OS-IMAGE             KERNEL-VERSION      CONTAINER-RUNTIME     LABELS
cl1vdrk0jb9kghvflo6u-uqus   Ready    <none>   42d   v1.29.1   10.131.0.14   51.250.44.130    Ubuntu 20.04.6 LTS   5.4.0-177-generic   containerd://1.6.28   beta.kubernetes.io/arch=amd64,beta.kubernetes.io/instance-type=standard-v3,beta.kubernetes.io/os=linux,failure-domain.beta.kubernetes.io/zone=ru-central1-d,kubernetes.io/arch=amd64,kubernetes.io/hostname=cl1vdrk0jb9kghvflo6u-uqus,kubernetes.io/os=linux,node.kubernetes.io/instance-type=standard-v3,node.kubernetes.io/kube-proxy-ds-ready=true,node.kubernetes.io/masq-agent-ds-ready=true,node.kubernetes.io/node-problem-detector-ds-ready=true,topology.kubernetes.io/zone=ru-central1-d,yandex.cloud/node-group-id=cat3kratir1ago3cbjif,yandex.cloud/pci-topology=k8s,yandex.cloud/preemptible=true
cl1vdrk0jb9kghvflo6u-ysyt   Ready    <none>   42d   v1.29.1   10.131.0.28   84.201.150.173   Ubuntu 20.04.6 LTS   5.4.0-177-generic   containerd://1.6.28   beta.kubernetes.io/arch=amd64,beta.kubernetes.io/instance-type=standard-v3,beta.kubernetes.io/os=linux,failure-domain.beta.kubernetes.io/zone=ru-central1-d,kubernetes.io/arch=amd64,kubernetes.io/hostname=cl1vdrk0jb9kghvflo6u-ysyt,kubernetes.io/os=linux,node.kubernetes.io/instance-type=standard-v3,node.kubernetes.io/kube-proxy-ds-ready=true,node.kubernetes.io/masq-agent-ds-ready=true,node.kubernetes.io/node-problem-detector-ds-ready=true,topology.kubernetes.io/zone=ru-central1-d,yandex.cloud/node-group-id=cat3kratir1ago3cbjif,yandex.cloud/pci-topology=k8s,yandex.cloud/preemptible=true

$ kubectl get nodes -o custom-columns=NAME:.metadata.name,TAINTS:.spec.taints
NAME                        TAINTS
cl1vdrk0jb9kghvflo6u-uqus   [map[effect:NoSchedule key:node-role value:infra]]
cl1vdrk0jb9kghvflo6u-ysyt   <none>

- Установка Loki и Promtail происходила из yc k8s marketplace
- Grafana уже была установлена в рамках прошлого ДЗ





