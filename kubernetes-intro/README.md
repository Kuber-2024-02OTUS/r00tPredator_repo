# Выполнено ДЗ №

 - [ ] В данном домашнем задании вы научитесь формировать локальное окружение, запустят локальную версию kubernetes при помощи minikube, научатся использовать CLI утилиту kubectl для управления kubernetes.

## В процессе сделано:
 - Установлен minikube, утилита   kubectl
 - Создан namespace.yaml
 - Создан pod.yaml

## Как запустить проект:
 - Запустить kubectl apply -f pod.yaml -f namespace.yaml в директории kubernetes-intro


## Как проверить работоспособность:
 - Зайти на поду и проверить что файл index.html создался в директории homework. 
 - Выполнить команду kubectl exec -it nginx -n homework -- /bin/sh 

## PR checklist:
 - [ ] Выставлен label с темой домашнего задания
