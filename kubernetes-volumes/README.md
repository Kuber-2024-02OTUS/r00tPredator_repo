# Выполнено ДЗ №

 [*] В данном домашнем задании вы научитесь формировать локальное окружение, запустят локальную версию kubernetes при помощи minikube, научатся использовать CLI утилиту kubectl для управления kubernetes.

## В процессе сделано:
- Создан манифест pvc.yaml, описывает PersistentVolumeClaim, запрашивает хранилище с storageClass по-умолчанию
- Создан манифест cm.yaml для объекта типа configMap
- В манифесте deployment.yaml изменена спецификация volume типа emptyDir, который монтируется в init и основной контейнер, на pvc, созданный в предыдущем пункте
- В манифесте deployment.yaml добавлено монтирование ранее созданного configMap как volume к основному контейнеру пода в директорию /homework/conf, его содержимое можно было получить, обратившись по url /conf/file

## Как запустить проект:
 - minikube start --driver=docker
 - kubectl apply -f namespace.yaml
 - kubectl label nodes minikube homework=true
 - kubectl apply -f cm.yaml
 - kubectl apply -f pvc.yaml
 - kubectl apply -f deployment.yaml
 - kubectl apply -f service.yaml
 - kubectl apply -f ingress.yaml

## Как проверить работоспособность:
 - curl http://homework.otus/homepage/conf/file
Output:
```
key1=value1
key2=value2
key3=value3
key4=value4
```
 - curl http://homework.otus/homepage
Output:
```
<html><head></head><body><header>
<title>http://info.cern.ch</title>
</header>
```

## PR checklist:
 [*] Выставлен label с темой домашнего задания
