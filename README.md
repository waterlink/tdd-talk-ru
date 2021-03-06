# Test-Driven Development

*(доклад, вебинар Top-Engineer)*

Oleksii Fedorov

That TDD Fellow

@waterlink000



## Порча кода

Note:
Порча кода - это реальная проблема, с которой множество команд сталкивается. Проявляется это в виде постоянно растущих сроков, на задачи, которые должны занимать меньше времени.


### Как код портиться

Note:
С каждой новой фичей, код становиться более сложным. Логика в коде начинает дублироваться, имена и комментарии устаревают и начинают лгать. Очень сложно понимать код.


### Как не дать коду портиться

Note:
Не давать логике дублироваться, поддерживать имена релевантными и самоописывающими, разбивать большие функции и объекты по частям. Короче говоря, чистить код.


### Почему сложно чистить код

Note:
Чистить код сложно. Потому что каждая чистка имеет риск создать один или несколько багов. Большие чистки точно вернутся от QA с длинным списком дефектов. Легче будет выкинуть чистку, нежели исправить дефекты.



## Набор автоматизированных тестов

Note:
Что если бы у нас имелся такой набор тестов, что ни один баг не может пробиться сквозь него в продакшн? И он исполняется за несколько минут?


### Длина списка багов

Note:
Длина списка багов это очень точный индикатор профессионализма команды разработки. Такой набор тестов сделает наш список багов очень маленьким.


### Страх изменений кода

Note:
В классической системе без тестов, каждое изменение в коде имеет большой риск создания новых багов. Такой риск ведет к страху изменений кода. Такой набор тестов убирает этот страх.


### Как же создать такой набор тестов?



## TDD, как дисциплина

Note:
TDD это такая же дисциплина для разработчиков, как у докторов мыть руки перед операцией, как спарринговые правила в боевых искусствах, как двойная запись у бухгалтеров.


### Три закона TDD

Note:
TDD имеет жесткие правила, которым все должны следовать. Правила могут звучать глупо, это ОК. Доктора в 1850 тоже думали, что мыть руки перед операцией - глупо. Бухгалтеры 500 лет также думали о 2й записи.


### 1. Пиши продакшн код только, чтобы исправить непроходящий тест


### 2. Пиши тестовый код только, чтобы показать непроходящий тест

Note:
Ошибка компиляции или ошибка парсинга (для компилируемых и интерпретируемых языков программирования, соответственно) это непроходящий тест.


### 3. Пиши продакшн кода не более, чем достаточно, чтобы исправить непроходящий тест

Note:
Это означает, что глупое `return true` или `return 0` это то, что нужно написать, если это делает все тесты проходящими.


### Глупые и строгие правила

.. на первый взгляд ..

Note:
Представьте, что команда разработки следует этим 3м правилам. Выбери одного человека из них, 1-3 минуты назад все работало корректно.


### Как много они пользуются дебаггером?

Note:
Очень-очень мало. Обычно дебаггинг выглядит так: CTRL+Z несколько раз, пока тесты опять не начнут проходить. Когда так мало времени инвестировано в дефект, удалить его очень легко.


### Сложные баги все-равно будут появлятся

Note:
Если применять эти 3 правила, то частота таких багов, на моем опыте, как минимум в десятки раз меньше.


### Идеальная документация

Note:
..для разработчика. Хочешь знать, как создать объект, он создается в тестах любым образом он может быть создан, вызвать функцию, она вызывается в тестах любым образом она может быть вызвана. Никогда не устаревает.


### Сперва тест

Note:
Сперва тест вынуждает код быть легко тестируемым. Синоним "легко-тестируемый код" это "низко-сцепленный код". И как мы знаем, низко-сцепленный код - одно из условий хорошего дизайна кода.


### Страх поломать работающий код

Note:
Код портиться, потому что программисты слишко бояться менять код, который работает, опасаясь, что он поламается. Как результат, никто не чистит код.


### Зеленая кнопка

Note:
Что если у вас была бы кнопка, которая при нажатии, после 5-30 секунд, говорила бы вам, что все приложение работает правильно или неправильно с указанием конкретно, что именно неправильно?


### Ваш парашют

Note:
Что если бы вы доверяли вашему набору тестов также, как сложеному вами парашюту перед прыжком? Что если бы ваш набор тестов исполнялся за 5-30 секунд для всего приложения?


### Бесстрашный рефакторинг

Note:
Такой набор тестов устраняет всякий страх при изменении кода. Соответственно, это дает возможность осуществлять бесстрашный рефакторинг. (привести пример тут).


### TDD устраняет страх изменения кода

Note:
Если вы будете следовать 3м правилам TDD, вы будете уверены что каждая строка продакшн кода была написана для того, чтобы исправить непроходящий тест. (каждая поломка не останется незамеченной)



## Набор тестов и дизайн кода

Note:
Давайте рассмотрим, как набор тестов может влиять на дизайн кода.


### Идеальный дизайн кода без тестов

Note:
Вы будете бояться делать изменения и рефакторинг и с каждой новой фичей, дизайн кода будет деградировать и код будет портиться.


### Ужасный дизайн кода, но ~100% тест-покрытие

Note:
Вы будете делать бесстрашный рефакторинг и сможете чистить код регулярно и улучшать дизайн кода с каждой новой фичей.


### Как добиться гибкости вашей системы?

Note:
Проще говоря, если вы хотите иметь гибкую систему, крайне важно, заиметь себе набор тестов, которому вы можете доверять всецело, и который исполняется за очень короткое время (5сек - 3мин).


### TDD - самый лучший способ получить такой набор тестов


### Другой способ: Тест-потом или "Дырявые" тесты

Note:
Ощущается, как ненужная/лишняя работа. Сложно тестировать ф-ию -> решение не тестировать ее (знаете, что работает) -> "дырявые" тесты -> нет доверия к этому набору тестов -> страх -> порча кода.



## Q & A

Note:
До сих пор, я не видел ничего, чтобы предотвращало и отменяло порчу кода, также хорошо и надежно, как TDD. Время для вопросов.



## Спасибо за внимание!

Twitter: [twitter.com/waterlink000](https://twitter.com/waterlink000)

Github: [github.com/waterlink](https://github.com/waterlink)

Блог: [tddfellow.com](http://tddfellow.com)
