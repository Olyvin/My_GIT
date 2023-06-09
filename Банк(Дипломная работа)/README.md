__Анализ клиентов регионального банка и выделение сегментов клиентов, склонных к уходу__

Заказчик исследования - маркетинговый отдел банка «Метанпром». Менеджер продукта.

__Цели исследования:__

Минимизация оттока клиентов банка на основе анализа их поведения.
Максимально эффективно выделить сегменты отточных клиентов, таким образом, чтобы маркетинговое воздействие на эти сегменты привело к уменьшению их оттока.

__Ход исследования:__

1  Описание задачи исследования

  1.1  Заказчик

  1.2  Цели исследования

2  Обзор данных:

  2.1  Загрузка датасета и общий обзор

  2.2  Проверка типов данных. Проверка уникальных значений

  2.3  Проверка на наличие пропусков

3  Предобработка данных:
  
  3.1  Приведение наименований столбцов к единому стилю
  
  3.2  Проверка на явные дубликаты
  
  3.3  Проверка на неявные дубликаты
  
  3.4  Кодирование категориальных признаков
  
  3.5  Анализ пропусков

4  Исследовательский анализ данных:
  
  4.1  Изучение показателей в разрезе оттока

  4.2  Дискретизация клиентов по возрастным группам
  
  4.3  Дискретизация клиентов по рейтинговым группам
  
  4.4  Изучение корреляции
  
  4.5  Определение портретов клиентов, которые склонны уходить из банка

5  Проверка статистических гипотез
  
  5.1  Проверка гипотезы о различии дохода между теми клиентами, которые ушли и теми, которые остались.
  
  5.2  Проверка гипотезы о том, что доход мужчин, в среднем, больше дохода женщин

6  Сегментация на основе стратегических показателей
  
  6.1  Определение и опиисание сегментов по признакам оттока клиентов

7  Выводы и рекомендации




Ссылка на дашборд: https://public.tableau.com/views/_16806518831600/Dashboard1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

Ссылка на презентацию: https://disk.yandex.ru/i/JtQoqvB__D19IA

__Выводы и рекомендации:__

Заказчиком исследования (маркетинговый отдел банка ) поставлена задача выявления сегментов клиентов, склонных к оттоку, на основе анализа их поведения, для разработки маркетинговых мероприятий с целью минимизации оттока клиентов банка.

Изучив предоставленный датафрейм увидели следующее: в датафрейме 10 тыс строк и 12 столбцов в столбце "userid" все значения являются уникальными в "score" содержится 460 уникальных значения, пропусков в столбце нет в "city" содержится всего три уникальных значения: 'Ростов Великий', 'Рыбинск', 'Ярославль', пропуски отсутствуют. в "gender" только два уникальных значения 'Ж' и 'М', пропуски отсутствуют "age" содержит 70 значений, пропуски отсутствуют столбец "objects" состоит из 11 уникальных значений без пропусков в столбце "balance" - 6383 уникальных значения от 3768.69 до 250898.09, содержит 3617 пропусков данных, что составляет 36.17% от общего количества данных. столбец "products" - 4 уникальных значения без пропусков данных столбцы "creditcard", "loyalty", "churn" содержат по 2 уникальных значения и в них отсутствуют пропуски "estimated_salary" содержит 9999 уникальных значения от 11.58 до 199 992.48, без пропусков. Образовавшийся 1 дубликат на 10 000 значений будем считать случайным, ни от чего не зависящим и ни на что не влияющим.

Посмотрели на все потенциальные неявные дубликаты (совпадение по всем значениям кроме 'userid', 'balance', 'estimated_salary'), нашли 7 потенциальных пар дубликатов, однако, мы не можем с полной уверенностью сказать, что это дубликаты и их количество слишком мало, чтобы сместить показатели в исследовании. Принято решение ставить эти строки в датасете. При анализе значений столбца Balance было выявлено 36% пропусков данных (всего 3617 пропусков). Пропуски обнаружены только в филиалах в Рыбинске и Ярославле. Основываясь на исследовании данных были сделаны выводы, что пропуски образовались случайно при выгрузке, либо по невнимательности менеджеров, заполняющих данную таблицу.

На филиал в Ростове Великом приходится самый большой процент оттока клиентов (40%).

В Ярославле наибольший процент оставшихся клиентов (52,8%), при этом также достаточно большой процент оттока (39,8%).

В Рыбинске процент оттока и процент оставшихся клиентов примерно одинаковы, но ни одна из групп не преобладает.

Средний балл рейтинга уходящих клиентов ниже, чем у оставшихся (645.35 против 651.85), что может указывать на то, что клиенты с более низким рейтингом склонны к уходу. Средний возраст уходящих клиентов выше, чем у оставшихся (44.84 против 37.41), что может указывать на то, что клиенты старшего возраста, склонны к уходу. Количество объектов в собственности не имеет большого влияния на уход клиента. Баланс на счету уходящих клиентов примерно равен оставшимся. Количество продуктов, используемых клиентом, похож у оставшихся и уходящих клиентов. Уходящие клиенты в среднем реже используют кредитные карты, чем оставшиеся. Уходящие клиенты в среднем менее лояльны, чем оставшиеся. Ожидаемая зарплата не имеет большого влияния на уход клиента. Мужчины менее подвержены оттоку, чем женщины.

Самый большой филиал находится в Ярославле , в Рыбинске и Ростове- клиентов в 2 раза меньше .

Количество клиентов с возрастом 30-40 лет является самым высоким среди остальных возрастных групп. Количество клиентов начинает снижаться после 40 лет. Разделили клиентов на 8 возрастных групп: 17-25 лет, 25-30 лет, 30-40 лет, 40-45 лет, 45-50 лет, 50-60 лет, 60-65 лет и 65-92 года. Количество ушедших клиентов преобладает над оставшимися в банке в возрастной группе 50-60 лет

Большинство клиентов банка имеют рейтинг в диапазоне от 600 до 850. Выделяется пик количества клиентов с рейтнгом 850 (233 человека). Распределение клиентов по рейтингу смещено вправо, что может указывать на то, что банк стремится работать с клиентами, которые имеют более высокий рейтинг, чем с клиентами, которые имеют более низкий рейтинг. Гистограмма показывает, что клиенты, имеющие более низкий рейтинг(менее 400), больше подвержены оттоку.

Вычислив коэффициенты корреляции между категориальными и количественными переменными, увидели:

Коэффициент корреляции 0.58 между данными churn и objects указывает на умеренную положительную корреляцию между ними. Это может означать, что с увеличением количества объектов, связанных с клиентом, вероятность оттока клиента также увеличивается

Коэффициент 0.49 между churn и age может означать, что отток клинтов зависит от их возраста

Коэффициент 0.24 между churn и loyalty может означать, что лояльность клиентов влияет на их отточность

Замечена небольшая корреляция между age и loyalty, age и products

churn коррелирует с rostov с коэффициентом 0.27, а с полом клиента с коэффициентом 0.17

Клиенты, возрасной категории 50-60 лет наиболее отточны во всех филиалах, самая большая доля отточных этого возраста в Ростове(70%), также там преобладает доля отточных среди возрастных групп 45-50 лет(65%) и 60-65 лет(57%). В Ярославле отточных в группе 50-60 лет более половины всех клиентов этой возрастной категории.

Абсолютно все клиенты(100%) во всех городах имеют отток, при наличии у них 4 продуктов банка. В Ростове 90% отточных имеют 3 продукта банка. В Ярославле и Рыбинске 79% отточных имеют 3 продукта. Скорее всего это связано с тем, что клиенты не удовлетворены продуктами банка, они принимали предложения от банка использовать другие продукты из портфеля банка, однако, ничего так и не подошло.

Абсолютный отток имеют клиенты с низким рейтингом (ниже 400 балов). В Ростове все остальные клиенты со всеми рейтинговыми баллами более склонны(30% и больше) к оттоку, чем в других филиалах. Хотя во всех городах распределение остальных рейтингов в разрезе оттока примерно равноемерное. Значит, склонность клиентов к оттоку при более высоком рейтинге не влияет на желание уйти.

Во всех городах наблюдается различная степень оттока клиентов в разрезе количества обьектов в собственности клиента. Самый большой отток (40%) у клиентов Ростовского филиала, имеющих 1 обьект, далее идут клиеты с 9 и 5 обьектами, остальные имеют схожие проценты, за исключением клиентов с 2 обьектами, их отток в Ростове самый низкий (23%). В Рыбинске и Ярославле доли ушедших клиентов в данном разрезе значительно ниже, самым всоким показателем является отток 23% в Рыбинске у клиентов с отутствующей собственностью.

Не лояльные клиенты более склонны к оттоку, в Ростове отток по не лояльным клиентам составляет 41% и почти в 2 раза меньший отток по лояльным клиентам. По остальным филиалам показатели в 2 раза ниже.

Женщины более склонны к оттоку во всех филиалах, особенно большие показатели оттока среди женщин в Ростове (38%)

Были проверены 2 гипотезы:

О различии дохода между теми клиентами, которые ушли и теми, которые остались.
Для проверки гипотезы о различии средних значений в доходе клиентов, которые ушли и тех, которые остались, мы использовали двусторонний t-тест Стьюдента для независимых выборок, так как мы имеем две независимые выборки (отдельные выборки для клиентов, которые ушли и остались). Выборки достаточно большие, их std сопоставимы

Для проведения тестирования мы задали уровень статистической значимости alpha = 0.05, что означает, что мы готовы принять ошибку первого рода (отвергнуть нулевую гипотезу, когда она на самом деле верна) в 5% случаев.

Результаты тестирования показали, что p-value = 0.23, что больше уровня статистической значимости alpha = 0.05. Поэтому мы не можем отвергнуть нулевую гипотезу о том, что нет статистически значимых различий в доходе клиентов, которые ушли и тех, которые остались.

Гипотеза о том, что доход мужчин, в среднем, больше дохода женщин
Так как распределение в выбороках не является нормальным, мы воспользовались непараметрическим тестом, использовали критерий Манна-Уитни. Он позволяет оценить статистическую значимость различий между двумя выборками без предположений о распределении. В нашем случае полученное значение p-уровня значимости равно 0.41, что больше стандартного уровня значимости 0.05. Следовательно, мы не можем отклонить нулевую гипотезу и не можем считать различия в доходе между мужчинами и женщинами статистически значимыми.

Выделены несколько сегментов клиентов с высоким уровнем оттока:

Cегмент - Клиенты в возрасте от 50 до 60, имеющими 1 продукт банка и не являющиеся лояльными, процент оттока - 89.00%.
Рекомендации: так как возрастная категория данных клиентов приближается к пенсионному возрасту, можно предложить им продукт, который будет полезен для накопления средств или бонусов, которые можно будет использовать в комплексе с пенсионной картой.

Сегмент - Мужчины в возрасте от 45 до 50 лет, c 1 продуктом - процент оттока - 54.00%.
Рекомендации: Разработать программу лояльности для клиентов, входящих в указанный сегмент. Например, предоставить скидки на покупки в партнерских магазинах или дополнительные бонусы за использование банковских продуктов.

Сегмент - Клиенты из Ярославля в возрасте 45+ лет, не лояльные банку - процент оттока - 63.00%.
Рекомендации: Предложить клиентам индивидуальный подход к обслуживанию. Например, учитывать предпочтения клиентов при выборе банковских продуктов или предоставлять консультацию по вопросам инвестирования.

Сегмент - Мужчины в возрасте от 45 до 50 лет, c 1 продуктом - процент оттока - 54.00%.
Рекомендации: Выяснить, что является причиной достаточно не высокого рейтинга, организовать обучающие мероприятия для клиентов, входящих в указанный сегмент. Например, провести семинар по финансовому планированию или обучить клиентов использованию интернет-банкинга.

Cегмент - Женщины в возрасте от 45 до 50, из г.Ростов Великий" - процент оттока - 65.00%.
Рекомендации: Предложить клиентам более выгодные условия по использованию банковских продуктов. Например, снизить комиссии за обслуживание счета или предложить льготные условия по кредитованию. Также можно предоставить бонусы за использование интернет-банкинга или за перевод зарплаты на счет в банке. Таким образом перевести их в статус лояльных.

В целом, для предотвращения оттока клиентов необходимо уделять внимание потребностям клиентов и предлагать им индивидуальные решения, которые будут соответствовать их потребностям и интересам. Необходимо создавать благоприятную атмосферу взаимодействия с клиентами, предоставлять качественный сервис и решать возникающие проблемы в короткие сроки.

Для того чтобы оценить эффективность мер по предотвращению оттока, маркетологам рекомендуется регулярно проводить анализ данных и мониторинг отзывов клиентов. Это позволит оценить эффективность принятых мер и внести необходимые изменения в стратегию работы с клиентами.
