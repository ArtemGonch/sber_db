# Знакомство с Redis и Redis-cluster

## Установка

Для начала я установил Redis. Для этого понадобился Doker и командная строка. После установки с помощью Docker я проверил на работоспособность Redis.

![Проверка](https://sun9-10.userapi.com/impg/y0BCqmznLKltnyY5XhAUKmFlvz54tiscpAgyMg/bbPenkcImAk.jpg?size=1910x963&quality=96&sign=67104cc861c4a603bd52153c52bfc9a4&type=album)

Переходим к работе с кластером, начнем с просмотра [вот этого видео](https://www.youtube.com/watch?v=N8BkmdZzxDg), здесь довольно понятно и подробно все описано.

Далее я начал запускать Redis-cluster.
Я прописал все ноды в docker-compose и прописал конфигурационные файлы для каждой ноды

![compose](https://sun1-96.userapi.com/impg/sK1UtFs1mwhJUMwGytePAmRHKBmOUHBwqXDFag/uK93pdeM7N4.jpg?size=1882x956&quality=96&sign=bb1d08f802f0a9b0f9bb5ac976a9b15d&type=album)
![configs](https://sun9-6.userapi.com/impg/kZ4G177XNU4wpP3jbiQa9CwIXBVpijCVZg5mLw/t3Up_XYNPeo.jpg?size=1901x800&quality=96&sign=32fd27c91b8059afcd0c3c2004eb6a23&type=album)
![Текст с описанием картинки](https://sun9-39.userapi.com/impg/mApvpQj-EyhyzGIWnOPoco_mJwxw9EmWr_4fdw/8xgV5iCb_jU.jpg?size=1552x397&quality=96&sign=390e0601bcd0db4e2293668b6734c005&type=album)
![Текст с описанием картинки](https://sun9-20.userapi.com/impg/K7ntNftDEpw7N659Bbq8iORp5Ip85NZbYyNMvg/utJBouDHqmY.jpg?size=1600x592&quality=96&sign=e8e8e2c2b19a7b59d0b8b31b8fc26ae8&type=album)
![Текст с описанием картинки](https://sun9-47.userapi.com/impg/4vnoPdBVaF2UUWginEn2Db9XSk0ytS1D459-Ig/QoXEWf41bhM.jpg?size=1886x927&quality=96&sign=c25aa1c4dae70a1f5b9654e357da7728&type=album)

Теперь можно приступить к написанию команд на питоне(использовался notebook)

## Пример команд просто на Redis(без кластера)

Здесь показаны выполняемые команды и затраченное время.

![Текст с описанием картинки](https://sun1-14.userapi.com/impg/pA2Xvkj2-5xaG9-MQTgqdgCgdJF3Y1SEEgaGlg/Kd_VbQh6t3w.jpg?size=807x338&quality=96&sign=88fb906aafc33d8f67ab7f21b9264436&type=album)
![Текст с описанием картинки](https://sun9-75.userapi.com/impg/MIj5PhWv-vJDU9-HibXQcp-OTM_pnqXNqWfHdg/F0BURR1yEvM.jpg?size=1017x363&quality=96&sign=58930d9c3d3f1ed34176c882be7b88a7&type=album)

## Примеры команд с использованием кластера

Здесь показаны выполняемые команды и затраченное время.

![Текст с описанием картинки](https://sun1-99.userapi.com/impg/6lAej04YZUksQZv8VHRapRU024nAwR2oSlzaxQ/HKfX7D73Lzg.jpg?size=846x432&quality=96&sign=dc2af51c83db9fc3716405cdf8e15c4b&type=album)
![Текст с описанием картинки](https://sun1-55.userapi.com/impg/di8nKoi4DTIzRndvN81a0TtFsQ4kkUKbkB5rBA/S6O-24z07ak.jpg?size=712x320&quality=96&sign=6f7227a852f7fe1d76db05102ec6665f&type=album)

## Подведем итоги

Можно заметить, что для выполенния hkeys и zadd на кластере требовалось чуть больше времени, так как время затрачивалось на распределение по узлам(дополнительная трата времени, но зато повышается отказоустойчивость, ведь теперь если одна нода ляжет, то всегда есть другие ноды, которые могут помочь выполнять запросы). В остальных же командах время было примерно таким же.
