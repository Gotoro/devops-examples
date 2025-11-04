# English
This provides a simple webapp, which serves a frontend, backend and a database.
This will not start AS-IS(!) - this requires existing images in the repos.
## Project Overview
```code
help-webapp-example/
├── Chart.yaml                      # metadata and dependencies
├── values.yaml                     # default config
├── .helmignore                     # ignore files when packaging
|
├── charts/                         # chart dependencies
|
└── templates/                      # all the templates
    ├── NOTES.txt                   # print helpful info after install
    ├── _helpers.tpl                # template helpers / functions
    ├── deployment-frontend.yaml    # frontend
    ├── deployment-backend.yaml     # backend api
    ├── service-frontend.yaml       # frontend service
    ├── service-backend.yaml        # backend service
    ├── ingress.yaml                # ingress for publishing to web
    ├── hpa.yaml                    # Horizontal Pod Autoscaler
    └── networkpolicy.yaml          # netsec
```

## How to run
### Have:
- k8s cluster
- kubectl
- helm
- existing ingress

### Change:
host in ./values.yaml

### Install:
This downloads postgres
```helm
helm dependency build
```

Create a namespace
```kube
kubectl create namespace my-webapp-ns
```

Install the chart with the release name 'my-app'
```kube
helm install my-app . --namespace my-webapp-ns
```

Check the running pods
```kube
kubectl get pods --namespace my-webapp-ns -w
```

Read the status (NOTES.txt)
```kube
helm status my-app --namespace my-webapp-ns
```

Get the load balancer ip
```kube
kubectl get svc --namespace ingress-nginx ingress-nginx-controller -o jsonpath='{.status.loadBalancer.ingress[0].ip}'
```

Add line to /etc/hosts - we got the ip from previous step
```code
# Example:
192.168.49.2   chart-example.local
```

Now open the web at
http://chart-example.local
and
http://chart-example.local/api

# Russian
Веб-приложение состоящее из фронтенда, бэкенда и базы данных.
Приложение на застартуется КАК-ЕСТЬ(!). Тут уже понадобятся образы самих приложений бекэнда и фронтэнда из репозиториев.
## Обзор проекта
```code
help-webapp-example/
├── Chart.yaml              # метаданные и зависимости
├── values.yaml             # конфигурация по умолчанию
├── .helmignore             # игнорировать файлы при упаковке
|
├── charts/                 # зависимости
|
└── templates/              # все шаблоны
├── NOTES.txt               # вывести статус после установки
├── _helpers.tpl            # функции шаблонов
├── deploy-frontend.yaml    # фронтенд
├── deploy-backend.yaml     # API бэкенда
├── service-frontend.yaml   # служба фронтенда
├── service-backend.yaml    # служба бэкенда
├── ingress.yaml            # Ingress для публикации в веб
├── hpa.yaml                # Автоскейл
└── networkpolicy.yaml      # netsec
```

## Как запустить
### Что должно быть:
- k8s кластер
- kubectl
- helm
- существующий ingress

### Изменить:
host в ./values.yaml

### Установить:
Скачиваем postgres
```helm
helm dependency build
```

Новое пространство имен
```kube
kubectl create namespace my-webapp-ns
```

Устанавливаем чарт с названием релиза 'my-app'
```kube
helm install my-app . --namespace my-webapp-ns
```

Смотрим запустились ли поды
```kube
kubectl get pods --namespace my-webapp-ns -w
```

Статус (NOTES.txt)
```kube
helm status my-app --namespace my-webapp-ns
```

Получение IP-адреса балансировщика нагрузки
```kube
kubectl get svc --namespace ingress-nginx ingress-nginx-controller -o jsonpath='{.status.loadBalancer.ingress[0].ip}'
```

Добавляем строку в /etc/hosts - берем ip из прошлого шага
```code
# Пример:
192.168.49.2 chart-example.local
```

Открываем браузер
http://chart-example.local
и
http://chart-example.local/api
