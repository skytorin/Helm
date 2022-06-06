# Helm

## Использование minikube
Веб дашборд с информацией о класере
```
minikube dashboard
```
Создание сервиса в minikube
```
minikube service app-deployment
```

## Установка Helm через APT
``` 
curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
sudo apt-get install apt-transport-https --yes
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
sudo apt-get update
sudo apt-get install helm
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
helm install app chart_01/
```
Откат к предыдущей версии релиза
```
helm rollback my-app
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








