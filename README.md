# Домашнее задание к занятию «Helm» - Петр Петров

### Задание 1. Подготовить Helm-чарт для приложения

1. Необходимо упаковать приложение в чарт для деплоя в разные окружения. 
2. Каждый компонент приложения деплоится отдельным deployment’ом или statefulset’ом.
3. В переменных чарта измените образ приложения для изменения версии.

### Решение 1.

Проверка Helm-чарта

![Проверка Helm-чарта](images/1.png)

Генерация Development-манифестов

![Рендеринг Development](images/2.png)

![Рендеринг Development](images/3.png)

Генерация Production-манифестов

![Рендеринг Production](images/4.png)

![Рендеринг Production](images/5.png)

Kubernetes-ресурсы

![Kubernetes-ресурсы](images/6.png)

Ingress и Middleware

![Ingress и Middleware](images/71.png)

![Ingress и Middleware](images/7.png)

Проверка Frontend

![Проверка Frontend](images/8.png)

Проверка Backend

![Проверка Backend](images/9.png)

Вычисленные значения Helm

![Вычисленные значения Helm](images/10.png)

Упаковка чарта

![Упаковка Helm-чарта](images/11.png)

Проверка архива

![Содержимое Helm-архива](images/12.png)

### Задание 2. Запустить две версии в разных неймспейсах

1. Подготовив чарт, необходимо его проверить. Запуститe несколько копий приложения.
2. Одну версию в namespace=app1, вторую версию в том же неймспейсе, третью версию в namespace=app2.
3. Продемонстрируйте результат.

### Решение 2.

Проверка Helm-чарта командой lint и генерация Kubernetes-манифестов для первого релиза.

![13](images/13.png)

![14](images/14.png)

![15](images/15.png)

Проверка пространств имён app1 и app2 для размещения экземпляров приложения.

![16](images/16.png)

Два независимых экземпляра приложения myapp-v1 и myapp-v2 в namespace app1. Для каждого экземпляра созданы отдельные frontend и backend Pod и Service

![17](images/17.png)

Проверка изоляции Service в namespace app1. Каждый Service связан только с Pod своего Helm-релиза благодаря уникальной метке app.kubernetes.io/instance.

![18](images/18.png)

Развертывание третьего экземпляра приложения myapp-v3 в namespace app2. Frontend и backend работают независимо от экземпляров, размещённых в app1.

![19](images/19.png)

Проверка Endpoint в namespace app2. Сервисы третьего экземпляра приложения направляют трафик к соответствующим backend и frontend Pod.

![20](images/20.png)

Список Helm-релизов во всех пространствах имен. Подтверждено успешное развёртывание трех экземпляров приложения: двух в app1 и одного в app2.

![21](images/21.png)

Проверка состояния Deployment в пространствах имен app1 и app2. Все шесть Deployment имеют READY 1/1 и AVAILABLE 1.

![22](images/22.png)

