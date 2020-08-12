# Kubernetes 2

## Репозиторий GitHub

https://github.com/sergeyyurkin/arch-homeworks

```
git clone https://github.com/sergeyyurkin/arch-homeworks.git
```

## Установка

```
kubectl apply -f ./kubernetes-1/deploy
```

## Проверка

```
curl -H 'Host: arch.homework' http://arch.homework/otusapp/sergeyyurkin/health
```
