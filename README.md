# H e l m



## Установка Helm
Установка через APT
```bash
curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
sudo apt-get install apt-transport-https --yes
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
sudo apt-get update
sudo apt-get install helm
```
Ручная установка
```bash
export HELM_VERSION=v3.3.4
wget https://get.helm.sh/helm-${HELM_VERSION}-linux-amd64.tar.gz
tar zxvf helm-${HELM_VERSION}-linux-amd64.tar.gz
sudo mv ./linux-amd64/helm /usr/local/bin/
rm helm-${HELM_VERSION}-linux-amd64.tar.gz && rm -r ./linux-amd64
helm plugin install https://github.com/databus23/helm-diff --version v3.1.3
```

## Установка Helmfile
```bash
export HELMFILE_VERSION=v0.132.0
curl -LO "https://github.com/roboll/helmfile/releases/download/${HELMFILE_VERSION}/helmfile_linux_amd64"
sudo mv helmfile_linux_amd64 /usr/local/bin/helmfile
sudo chmod +x /usr/local/bin/helmfile
```

## Автодополнение команд bash
```
source <(helm completion bash)
helm completion bash > /etc/bash_completion.d/helm
```

## Команды Helm
Версия Helm
```
helm version 
```
Список чартов доступных на общем хабе
```
helm search hub
```
Список чартов из добавленных репозитариев
```
helm search repo
```
Просмотр всех релизов 
```
helm list
```
Просмотр статуса релиза
```
helm status my-app
```
Информация по Helm Chart
```
helm get all my-app
helm get notes my-app
helm get manifest my-app
helm get volues my-app
```
Автосоздание скелета Helm Chart в директорию app_auto
```
helm create app_auto
```
Инсталляция релиза из Helm Chart
```
helm install {app_name} {chart_dir/} -n {namespace}
```
Ревизия истории всех релизов
```
helm hitstory my-app -n namespace
```
Откат к предыдущей версии релиза
```
helm rollback my-app -n namespace
```
Откат к 5 ревизии релиза
```
helm rollback my-app 5 -n namespace
```
Удаление деплоймента Helm Chart со всеми сущностями 
```
helm uninstall app
```
или
```
helm delete app
```
Запаковать Helm Chart в tgz архив
```
helm package chart_01/
```
Изменения значений параметров в чарте
```
helm upgrade app chart_01 --set replicaCount=2 --set container.image=httpd:latest
```
Добавление репозитария bitnami
```
helm repo add bitnami https://charts.bitnami.com/bitnami
```

## Команды Helmfile
Сравнение изменений установленного релиза с чартом в репе
```
helmfile --kube-context <context> -n <namespace> -e <env> diff
```
Установка релиза
```
helmfile --kube-context <context> -n <namespace> -e <env> apply
```





