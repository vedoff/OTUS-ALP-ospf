# OSPF
## Создать домашнюю сетевую лабораторию. Научится настраивать протокол OSPF в Linux-based системах.
1. Поднять три виртуалки.
2. Объединить поднять OSPF между машинами на базе FRR.
3. Изобразить ассиметричный роутинг.
4. Сделать один из линков "дорогим", но что бы при этом роутинг был симметричным.

# Схема
![](https://github.com/vedoff/ospf/blob/main/pict/Screenshot%20from%202022-03-19%2019-32-16.png)

# Выполнение:
### Разворачиваем стенд и настраиваем настраиваем OSPF на маршрутизаторх.
`vagrant up && ansible-play play.yml`

Получим следующее после развертывания:

![](https://github.com/vedoff/ospf/blob/main/pict/Screenshot%20from%202022-03-19%2011-57-57.png)

![](https://github.com/vedoff/ospf/blob/main/pict/Screenshot%20from%202022-03-19%2012-02-23.png)

## Ассиметричный роутинг
Так как при развертывнии было сразу прописана на все роутеры\
`/etc/sysctl.conf` \
`net.ipv4.conf.all.rp_filter=0` \
Заходим на `Router1` и `Router2` изменяем: 
 - `net.ipv4.conf.all.rp_filter=0` на `net.ipv4.conf.all.rp_filter=1`
 - 
