# Статистический анализ данных сервиса аренды самокатов

## Цель проекта
---
В данном исследовании рассмотрим данные, полученные от сервиса аренды самокатов GoFast. Проанализируем данные о пользователях из разных городов и их поездках, составим и проверим гипотезы, которые могут помочь бизнесу вырасти.

Чтобы совершать поездки по городу, пользователи сервиса GoFast пользуются мобильным приложением. Сервисом можно пользоваться:

без подписки:

абонентская плата отсутствует;
стоимость одной минуты поездки — 8 рублей;
стоимость старта (начала поездки) — 50 рублей;
с подпиской Ultra

абонентская плата — 199 рублей в месяц;
стоимость одной минуты поездки — 6 рублей;
стоимость старта — бесплатно.
Цель работы состоит в изучении данных по пользователям сервиса аренды самокатов и поиске гипотез, которые помогут бизнесу лучше понимать своих клиентов. Также, одной из главных целей проекта является закрепление знаний, связанных со статистическом анализом.

Мы рассмотрим три разных файла с данными о пользователях, выполним предобработку данных и исследовательский анализ. Изучим такие фактора как: возраст пользователей; расстояние, которое пользователь преодолел за одну поездку; продолжительность поездок.

Проанализируем суммарное расстояние, количество поездок и суммарное время для каждого пользователя за каждый месяц, а также добавим данные по помесячной выручке, которую принёс каждый пользователь.

Затем приступим к рассмотрению и анализу следующих гипотез:

Важно понять, тратят ли пользователи с подпиской больше времени на поездки? Если да, то пользователи с подпиской могут быть «выгоднее» для компании.

Расстояние одной поездки в 3130 метров — оптимальное с точки зрения износа самоката. Можно ли сказать, что среднее расстояние, которое проезжают пользователи с подпиской за одну поездку, не превышает 3130 метров?

Проверьте гипотезу о том, будет ли помесячная выручка от пользователей с подпиской по месяцам выше, чем выручка от пользователей без подписки.
## Результат
---
Мы проанализировали три датасета сервиса аренды самокатов GoFast, загрузив их в датафреймы и проверив типы данных. Удалены дубликаты в датафрейме USERS.

Данные включают 8 городов России, большинство пользователей проживает в Пятогорске, а наименьшее – в Москве. Средний возраст пользователей – 25 лет, минимальный – 12 лет, максимальный – 45 лет. 54.4% имеют бесплатную подписку, 45.6% – подписку "ультра".

Изучены расстояния и продолжительность поездок: минимальное – около 1 метра, максимальное – 7211 метров. Среднее и медианное время поездок – 17,7 минут, максимальное – 40 минут, минимальное – 30 секунд, отфильтрованное как выброс.

Созданы новые датафреймы для пользователей с подпиской «ультра» и бесплатной подпиской, построены графики расстояний и времени поездок.

Агрегированы данные по идентификатору пользователя и месяцу, посчитаны суммарные расстояния и время поездок для каждого пользователя, а также общее количество поездок в месяц. Добавлен столбец с помесячной выручкой и выяснилось, что сервис заработал за календарный год на пользователях с подпиской около 1 млн.645 тыс. рублей, без подписки – около 2 млн.229 тыс. рублей. Средний доход от подписчика – 337 рублей в месяц, без подписки – 274 рубля.

Проверены гипотезы:
1. Пользователи с подпиской проводят больше времени в поездках.
2. Среднее расстояние за поездку меньше износа самоката (3130 метров).
3. Помесячная выручка от подписчиков выше, стоит рассмотреть варианты стимулирования.

Для проверки изменения количества обращений в техподдержку после обновления сервиса проанализируем выборки до и после обновления, используя функцию st.ttest_rel.

Рекомендации бизнесу:
- Увеличить количество клиентов с платной подпиской с помощью промоакций или скидок.
- Оптимизировать количество ремонтов и замены самокатов.
- Разработать сетку подписок: для студентов, семейную, по фиксированным значениям времени и расстояния поездок.
- Проанализировать и оптимизировать количество самокатов на стоянках в зависимости от загруженности локации.