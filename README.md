# GrayMonk90_platform
GrayMonk90 Platform repository

## Занятие 2: знакомство с Kubernetes, основные понятия и архитектура
В ходе выполнения домашней работы была подготовлена репа к GA, на тачку установлены minikube, kubectl, kind и k9s. Дополнительно развернул Kubernetes Dashboard, но по итогу им не пользовался, поскольку k9s стал для меня приятным открытием.  

Изучил восстановление подов из `kube-system` неймспейса.  

Написал Dockerfile с web-server'ом, за основу взял `nginx:1.21.6-alpine`, запушил образ в docker hub и развернул под с этим образом, используя [манифест](kubernetes-intro/web-pod.yaml). После подключения init-контейнера, смог увидеть сгенерированный index.html (лого красивое :thumbsup:).  

Собрал фронт microservices-demo, развернул с помощью `kubectl run ...`, сохранил манифест (`-o yaml > frontend-pod.yaml`). Исправил ошибку при запуске пода, исправления внес в [манифест](kubernetes-intro/frontend-pod-healthy.yaml).
