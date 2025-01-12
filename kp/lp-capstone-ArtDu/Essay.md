# Реферат
## по курсу "Логическое программирование"

### студент: Дубинин А. О.

## Логические языки и базы данных

## Результат проверки

| Преподаватель    | Дата        |  Оценка      |
|-------------------|--------------|---------------|
| Сошников Д.В. |   22.12.18           |   5           |
| Левинская М.А.|              |              |

> Оригинальная реализация заданий 4 и 5

## Дедуктивная база данных

База данных представляет собой организованное собрание информации, которая обычно хранится в электронном виде на компьютере. А конкретно дедуктивная база представляет собой объединение логики и стандартных баз данных. Эта система оперирует уже предписанными логическими фактами, правилами и с помощью них может делать вывод или записывать новые факты. Конечно, дедуктивная база не просто смешение двух концепций, эта база обладает главным свойством всех баз, она умеет быстро и качественно оперировать огромным пластом данных. Язык Datalog же является один из способов записи фактов и правил. В недавнее время применение таких баз увеличилось в сферах, которые не были так популярны раньше, например облачные технологии. Язык prolog схож с языком datalog, но различия всё же существуют:

* В языке пролог влияет, где расположен тот или иной предикат, тем самым ответ будет разный, при выполнении одних и тех же предикатов ну в разных строчках расположения. Это свойство нужно для эффективных программ В отличии же от баз данных(datalog или sql), где расположение не играет никакой роли.

* В прологе присутствуют средства, которые изменяют ветки доказательств. Пример, предикат cut(!).

* Создание сложных символов из функциональных не допускается в дедуктивных базах данных.

### Подробнее о дедуктивных баз данных

Дедуктивная база данных состоит из фактов и правил, которые выводят новые факты на основе запроса пользователя и предварительно данных фактов.

И, следовательно, к этому определению может подходить и обычная SQL СУБД. В качестве SQL баз элементом определения может оператор SELECT, и правда, результатом этого оператора будет другая таблица.

Отличием же является, что при доказательстве правила в дедуктивных базах данных может присутствовать рекурсия. Безусловно есть плюсы от рекурсии в дедуктивных системах, но есть и минусы. Когда нужно будет составить рекурсивное правило, SQL ориентированная база будет иметь большие проблемы, в то время, как дедуктивная легко справится с задачей, но есть и обратная сторона, эффективность поиска страдает, особенно при больших данных.

Не вдаваясь в подробности реализации внутренности этого типа базы. Скажем одно, внутри реализации состоит из логических запросов и определений, поэтому её и называют логической БД. Так же можно сказать, что реализация похожа на Базу Знаний, по сути интенсиональная часть дедуктивной БД и есть БЗ.

Так же, что ещё можно сказать о реализации, дедуктивная БД основана на реляционной СУБД, эта система выступает в роле базы фактов и исполнителя запросов, которые поступают с более высокого уровня, то есть из дедуктивной БД.

Есть разница между обычным использованием SQL базы, и тем как дедуктивная база данных использует эту SQL базу. Обычно мы используем СУБД, отправляя ей один запрос, тут же дедуктивная система отправляет пакетный запрос к реляционной СУБД. Сделано это для оптимизации, пакет запросов оптимизируется совместно

Правила нельзя хранить вечно в оперативной памяти, по причине расширения количества правил, что физически не хватает памяти. Тут возникает вопрос, как же разместить во внешней памяти эффективно. Были попытки применять здесь тоже реляционную бд, но пока общего решения не придумали.



### Подробнее о datalog

Datalog язык, который по написанию похож на prolog, это основной язык, которым пользуются для работы с дедуктивными базами.

Его автором считается Давид Майер, именно он со своей коллегой Эрве Галлер организовал в 1977 лекцию по логики, на которым впервые прозвучал термин Datalog.

#### Особенности, ограничения и расширения

В отличие от Пролога, утверждения программы Datalog могут быть изложены в любом порядке. Более того, запросы Datalog на конечных множествах гарантированно завершаются, поэтому Datalog не имеет оператора cut Prolog'а. Это делает Datalog полностью декларативным языком.

В отличие от Пролога, datalog:

1. В качестве аргумента предиката не может присутствовать сложный термин, например E(1,G(2,4)).
2. накладывает определенные стратификационные ограничения на использование отрицания и рекурсии.

Оценка запросов с использованием Datalog базируется на предикатах первого порядка и, следовательно, является надежной и полной. Datalog не полный по Тьюрингу и поэтому используется как предметно-ориентированный язык, является эффективным и может использовать мощные алгоритмы запросов.

## База знаний

База знаний - это база, хранит информацию, которая изначально хранится в базе или которая могла быть получена путем решения предыдущих задач или изначально заданы какие знания и правила оперирования этой информацией.

Сегодня базы знаний работают с большим пластом информации, находя её средствами систем поиска, для поиска этой информации нужна определенная модель и формат этих самых данных. Вся информация хранится иерархически, то есть все понятия и их отношения.

Главное отличие от обычных баз данных, в том, то помимо данных в базе знаний присутствует правила, которые составляют заключение по уже введенным фактам и так база знания оперирует информацией.

База знаний широко связана с искусственным интеллектом, сама наука объединяющая эти две сферы называется инженерией знаний.

### Применение

Как уже выше было сказано, искусственный интеллект основное применение базы знаний. Самое часто применяемое в последнее время это группа экспертных систем, направленных на решения проблем конкретной области, взяв за основу данные пользователя и начальную базу данных.

Пользы от этих систем много, ну основная польза заключается в том, что для решения какой-либо простой задачи, которую, не оперируя нужными знаниями человек, решить не в силах, не нужный специально обученный персонал, то есть менее опытный человек, может либо обучаться, либо быстро находить решение.

### Базы знаний и интеллектуальные системы

Информация в базах знаний должна быть всегда самая последняя и истинная, чтобы интеллектуальная система работала корректно, это главные требования к информации, хранящийся в базе.

Так же присутствуют множество хороших требований, ну по стандарту они не обязательны, например:
* Вывод свежих новых данных из старых.
* Кроме вывода истинности заключение, должны присутствовать шаги решения.
* Нахождение не состыковок или противоречий.
* Нахождение закономерностей из изложенных раннее данных.

Другими словами, оснащая систему самообучением, нет предела, чтобы усовершенствовать её функционал.


### Базы знаний в Prolog'е

Базы знаний в Prolog'e это по сути факты и правила, которые представляют различную информацию, главное чтобы факты и правила были логически верными. То есть, при запросе пользователя пролог сообщает истина это или ложь, попутно оперирую ранее заданными фактами и правилами.

## Выводы

Исследовав текущее положение дел в современном использовании баз данных и систем логического программирования, я пришел к выводу, что они испытывают упадок. Существуют отдельные интересные проекты, но их несопоставимо мало по сравнению с базами данными, не связанными с логикой. Однако, это не отменяет научного интереса человечества к автоматическому доказательству теорем и математической логике в целом. Я считаю, что с дальнейшим развитием систем искусственного интеллекта, к которым в наше время обществе проявляет подлинный интерес, будет реализован новейший язык логического программирования, который будет иметь самую современную базу данных связанную с логикой, который учтёт все недостатки его предшественников, и станет панацеей разработчиков, имеющих дело с системами максимально близкими к человеческому мышлению.

## Список использованной литературы

Чери С., Готлоб Г., Танка Л. Логическое программирование и базы данных. — 1992. 352 с. (ISBN 5-03-002472-7)

http://logic.stanford.edu/jarvis/complaw/ddb.html
https://en.wikipedia.org/wiki/Datalog
https://ru.wikipedia.org/wiki/Дедуктивная_база_данных
http://citforum.ru/
