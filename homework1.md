# ДЗ №1. Знакомство с MongoDB

## Установка

MongoDB я устанавливал через [официальный сайт](https://www.mongodb.com/). При установке я также скачал и MongoDBCompass (в котром можно всё пронаблюдать визуально), в конце я скачал MongoDBShell через тот же [официальный сайт](https://www.mongodb.com/).

В cmd после скачивания я написал команду mongosh, из котрой извлёк локальный андрес, на котром была развёрнута MongoDB; с помощью этого адреса я установил соединение в MongoDBCompass.

## Создание БД и заполнение данными

Датасет я взял [отсюда](https://habr.com/ru/company/edison/blog/480408/); решил выбрать вариант [Wine quality dataset](https://archive.ics.uci.edu/dataset/186/wine+quality)— более 6 000 записей с характеристиками вин. Итого вот как это отображается в MongoDBCompass:

![Общий вид](https://sun9-7.userapi.com/impg/qTAqrWIg85U82SGJT-jCCtQdh5a1719ZxN162Q/WIUVums14Kc.jpg?size=1771x981&quality=96&sign=e2ea43a548205a0113c8be13c704dae5&type=album)

## Операции

Теперь же мы будем работать в MongoDBShell. Будем выполнять операции CRUD. Начнем с findOne:

![Текст с описанием картинки](https://sun9-19.userapi.com/impg/ELLniNs76kAx7RSxq3Meki5yOIR4kWxg6Po_dw/VqYr5u7YZTA.jpg?size=1162x532&quality=96&sign=5cb619263ab736eafc7e828da64632b7&type=album)

Теперь же попробуем findMany с использованием sort и limit:

![Текст с описанием картинки](https://sun9-3.userapi.com/impg/hUnxNYdlaxUNTnysKyC7lr__NrgJ-ySgVWKYUg/2KF1UmUvrPQ.jpg?size=1707x755&quality=96&sign=97883998f28fd4aa1649d9b7b85d88b1&type=album)

Далее будем замерять ещё и время исполнения команд. Запустим команду, использующую оператор $gt и замерим время:

![Текст с описанием картинки](https://sun9-30.userapi.com/impg/hcLEOHdO388J-YSrGrezkGBfqCrEFL1RR__joA/FYu9nvhHMq8.jpg?size=926x452&quality=96&sign=d8acb7f956f07b685342d0979fdd173b&type=album)

Как видим, время исполнения 5 миллисекунд.

Далее операция updateOne. Произошла операция мгновенно.

![Текст с описанием картинки](https://sun1-85.userapi.com/impg/WfLUoETUs6atIHia_AGt5sOt5yYddQbaiMBsuQ/eGSQh3rYRcI.jpg?size=767x250&quality=96&sign=2013f93c9e38f2896453057bf191e8ef&type=album)
![Текст с описанием картинки](https://sun1-17.userapi.com/impg/8vonfFsoHeviv2cxiLJVGlnaq8zDZIHgAdG0Fg/aRHQ9TMucDc.jpg?size=957x517&quality=96&sign=e58c28877b0526ffd69aa47bb6d5030b&type=album)

Теперь операция updateMany. Заняла 162 миллисекунд.

![Текст с описанием картинки](https://sun9-55.userapi.com/impg/wbUumwm3D65YymmuERaD5qqxWQ8r4QaSgdCM1A/v1oVsYU95u8.jpg?size=1378x772&quality=96&sign=999d0949784fd454b0b38e93cda06792&type=album)

Операция deleteOne(прошла мгновенно).

![Текст с описанием картинки](https://sun9-24.userapi.com/impg/BpYc-1DJ_Eoy0DuvIoG6zidsY4uDoEWuYRCqcQ/VtUKQlXlQvM.jpg?size=1197x478&quality=96&sign=1c228f9887a86cfb2bc201ad72d946f0&type=album)

Операция deleteMany. Было удалено 193 документа, сама операция заняла 1461 миллисекунду.

![Текст с описанием картинки](https://sun9-49.userapi.com/impg/4jpeG5zgSpEVH-Nh6fQfpHwgq3BvAEQv7j3big/X5_La4zByAY.jpg?size=1101x481&quality=96&sign=bb11d993725bd654fd78bd9c375c2d2e&type=album)

Операция insertOne. Произошла операция мгновенно(1 мс).

![Текст с описанием картинки](https://sun9-59.userapi.com/impg/jn1_pfKZs3Kpf3C9lSMBWGhqW0kQzYQUuNVO6g/fhIaD0mBA14.jpg?size=697x150&quality=96&sign=97b4d0d6cb7e6ff2396c3393e958f338&type=album)

![Текст с описанием картинки](https://sun1-20.userapi.com/impg/yuy7Lp1XtbWU--icIbey0eNS4GQGT6CCFYKXSg/_y_2rOYivEk.jpg?size=986x600&quality=96&sign=0b6b5291eec42f7452f640d604ff39ae&type=album)

Операция insertMany. Произошла операция мгновенно.

![Текст с описанием картинки](https://sun9-7.userapi.com/impg/xU_HqgEqi1kW7jdjAV--gUgVNo6gnkcSydKb9Q/U3lHYuM0cZk.jpg?size=1275x273&quality=96&sign=aa4505d1190afd86a4166d1e47c64b27&type=album)

![Текст с описанием картинки](https://sun1-92.userapi.com/impg/EFNklgzUBay0PkSzw1qZZ3HfG9AZrxyzGMaScA/_SvjwKz5uY0.jpg?size=955x776&quality=96&sign=64f02ba1501d3ebd8bfee6827b8e84c5&type=album)

![Текст с описанием картинки](https://sun9-19.userapi.com/impg/tQcLu3btcty_V-GKN_xmf55A0nbOGIYqcKRBWA/673zwCOTZyA.jpg?size=832x193&quality=96&sign=330b01deeecbcee5dc104ec40fcf1f51&type=album)

## Создание индекса и сравнение времени работы

Создадим индекс.

![Текст с описанием картинки](https://sun9-61.userapi.com/impg/xQx3Z9sld2RWiBswBEgDJMV4NFMa5ZErn-JeLw/E2mENJJLZPE.jpg?size=522x70&quality=96&sign=39544f2dedc1aac987c06a3ed049a905&type=album)

После сравним время работы по поиску всех экземпляров. Как мы видим стало 8 миллисекунды, что на порядок быстрее без использования индекса.

![Текст с описанием картинки](https://sun9-58.userapi.com/impg/eSGXbyq_QQrR5SQaEH0TMH3j6VqbqEJGcVNHcA/1RLzfEn3xAg.jpg?size=953x460&quality=96&sign=a2b46cbb2b0e9296efcbd99d4001788f&type=album)

Далее проведем операцию вставки. Вот здесь уже 18 миллисекунд, что намного дольше случая без индекса.

![Текст с описанием картинки](https://sun1-89.userapi.com/impg/OzsQOQ7b2_1EesTjyx7z2c4iwYemq6OCeS0D9w/mrWmdddqWhk.jpg?size=933x482&quality=96&sign=3d8588acaacc3edea08d14bc959acb53&type=album)

И осталось только обновление. Заняла 38 миллисекунды, что на порядок быстрее, чем раньше.

![Текст с описанием картинки](https://sun1-84.userapi.com/impg/r16-vGP4eQFwbx787W2msTnfUvn4I2WdaLdIJg/OF-CXS-vhOw.jpg?size=995x750&quality=96&sign=9daf54b8a91af83959e2ab2f2dc8ca27&type=album)
