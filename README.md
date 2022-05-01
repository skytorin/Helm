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
Просмотр всех релизов 
```
helm list
```
Автосоздание шаблонов файлов для нового чарта
```
helm create app_auto
```
Инсталляция релиза из шаблонов чарта
```
helm install app chart_01/
```
Деинсталляция релиза 
```
helm uninstall app
```
Изменения значений параметров в чарте

```
helm upgrade app chart_01 --set replicaCount=2 --set container.image=httpd:latest
```


