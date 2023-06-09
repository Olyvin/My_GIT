__Оценка результатов А/В теста__

  __Цели исследования:__

Проанализировать данные и проверить их соответствие требованиям технического задания.

Оценить корректность проведения A/B-теста и выявить возможные ошибки или проблемы.

Провести исследовательский анализ данных и определить особенности, которые нужно учесть перед проведением A/B-тестирования.

Оценить результаты A/B-тестирования и проверить статистическую разницу долей.

  __Ход работы:__
  
  1 Загрузка файлов и исследование данных
  
  2 Лайфтайм
  
  3 Совпадение теста и маркетинговых событий
  
  4 Пересечение тестовой аудитории с другими тестами:
  
  5 Распределение количества событий на пользователя и тест на равенство событий.
  
  6 Воронка событий
  
  7 Проверка статистической разницы долей z-критерием.


__Техническое задание:__

- Название теста: recommender_system_test;
- Группы: А (контрольная), B (новая платёжная воронка);
- Дата запуска: 2020-12-07;
- Дата остановки набора новых пользователей: 2020-12-21;
- Дата остановки: 2021-01-04;
- Аудитория: 15% новых пользователей из региона EU;
- Назначение теста: тестирование изменений, связанных с внедрением улучшенной рекомендательной системы;
- Ожидаемое количество участников теста: 6000.
- Ожидаемый эффект: за 14 дней с момента регистрации в системе пользователи покажут улучшение каждой метрики не менее, чем на 10%:
  - конверсии в просмотр карточек товаров — событие product_page
  - просмотры корзины — product_cart
  - покупки — purchase.

__Выводы:__

В рамках данного проекта была проведена оценка корректности проведения А/B теста, проанализированы результаты теста, исследованы пересечения тестовой аудитории с конкурирующим тестом, совпадение теста и маркетинговых событий, а также другие проблемы временных границ теста.

Изучив данные, были сделаны несколько выводов:

Файл final_ab_events.csv содержит информацию о действиях пользователей, которые принимали участие в А/В-тестировании. Всего в файле 4 столбца и 440317 строк.

В файле ab_project_marketing_events.csv содержится информация о маркетинговых мероприятиях, проведенных в течение года. Файл содержит 14 строк и 4 столбца.

В столбце details файла final_ab_events.csv имеется 85,75% пропусков. Необходимости их заполнять пока не выявлено.

В столбцах event_dt, start_dt и finish_dt содержится информация о датах в формате object. Эту информацию нужно преобразовать в формат datetime для удобства дальнейшей работы.

В столбце details содержится информация о стоимости покупки. Возможно, что некоторые пользователи не совершали покупок и в этом случае в столбце могут присутствовать пропуски.

В столбце regions файла ab_project_marketing_events.csv есть значение EU, CIS, APAC, N.America, которое может затруднить дальнейший анализ, так как необходимо выделить каждый регион отдельно.

В столбце regions отсутствуют пропуски.

В файлах нет дубликатов.

Анализируемый тест имеет пересечение с конкурирующим в 1602 пользователея. Это не малое количество, и следует учесть, что это могло повлиять на результаты теста.

Разница в количестве пользователей в группах составляет более 14%, что также могло влиять на результаты теста.

В момент проведения теста проводилась промо-акция 'Christmas&New Year Promo'. Понять, что именно изменения вызывают улучшения, а не параллельно проводимая акция, в таком случае крайне затруднительно.

Фактическое количество пользователей из Европы в тесте - 15%, что соответствует уровню, заданного в ТЗ.

События по дням распределены не равномерно, среднее количество событий на пользователя в группе А - 7, а в группе В - 6, пик около 21 декабря объясним ажиотажем перед Рождеством. Однако несмотря на то, что окончание теста заявлено 4 января, события в таблице заказчиваются 30 декабря. Возможно, это проблема с выгрузкой. Явного всплеска активности в период попадания в период маркетинговой активности не наблюдается.

Разница в количестве событий группы В и группы А - 72.96%, что говорит о неравномерном распределении выборок.

В наших данных 14 дней прожили пользователи, зарегистрировавшиеся с 07.12.2020 по 22.12.2020. Начиная с регистрации от 23.12.2020 данные неполные. Кроме того, т.к. по техническому заданию мы анализируем воронку на 14 день жизни - события более 14 лайфтайма нам также не нужны.

Все пользователи из обеих групп в нашей выборке после регистрации залогинились. Переход на шаг 'product_page' (карточка товара) совершили 65% из контрольной группы А и 56% из тестовой группы В, что говорит об ухудшении конверсии в тестовой группе на данном шаге. В воронке следующим по численности пользователей идет шаг 'purchаse', что говорит о том, что многие пользователи игнорировали этап просмотра корзины и делали покупку минуя этот шаг. Из 'product_page' в 'product_cart' конвертировались в группе А 46% пользователей и почти 50% в группе В. В 'purchаse' из 'product_cart' конвертировалось 106% в контрольной группе и чуть более 100% в тестовой группе. Конверсия залогинившихся пользователей в покупателей составила 32% в контрольной группе и более 27% в тестируемой.

Исходя из этих факторов, можно сказать, что тест нуждается в дополнительном анализе и улучшении, чтобы получить более точные и достоверные результаты.

При проведении А/В тестирования z-критерием гипотезы о равенстве конверсий в группах А и В не удалось подтвердить. Это означает, что они различаются. Мы подтвердили выводы, сделанные в результате исследовательского анализа: конверсии различаются, и не в лучшую сторону, следовательно предлагаемые к внесению изменения, которые были целью тестирования, не будут эффективными.
