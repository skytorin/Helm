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
Автосоздание скелета Helm Chart в директорию app_auto
```
helm create app_auto
```
Инсталляция релиза из Helm chart
```
helm install app chart_01/
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








