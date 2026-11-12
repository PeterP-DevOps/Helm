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

