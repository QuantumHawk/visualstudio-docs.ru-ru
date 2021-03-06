---
title: Набор правил "Рекомендуемые правила для машинного кода"
ms.date: 11/04/2016
ms.topic: reference
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4a86cb62fe0ae0db971a417ef923f45eedbefe0c
ms.sourcegitcommit: ade07bd1cf69b8b494d171ae648cfdd54f7800d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81649284"
---
# <a name="native-recommended-rules-rule-set"></a>Набор правил "Рекомендуемые правила для машинного кода"

Рекомендуемые правила коренных народов сосредоточены на наиболее важных и распространенных проблемах в родном коде, включая потенциальные дыры в безопасности и сбои приложений. Этот набор правил включает в себя все правила в наборе [правил «Минимальные правила коренных](native-minimum-rules-rule-set.md) народов».

Включите это правило, установленное в любой набор пользовательских правил, который вы создаете для нативных проектов.

|Правило|Описание|
|----------|-----------------|
|[C6001](../code-quality/c6001.md)|Использование неинициализированной памяти|
|[C6011](../code-quality/c6011.md)|Разыменование пустого (NULL) указателя|
|[C6029](../code-quality/c6029.md)|Использование значения unchecked|
|[C6031](../code-quality/c6031.md)|Возвратное значение проигнорировано|
|[C6053](../code-quality/c6053.md)|Вызов завершается нулем|
|[C6054](../code-quality/c6054.md)|Нулевое прекращение отсутствует|
|[C6059](../code-quality/c6059.md)|Неверное объединение|
|[C6063](../code-quality/c6063.md)|Пропущен строковый аргумент функции форматирования|
|[C6064](../code-quality/c6064.md)|Пропущен целочисленный аргумент функции форматирования|
|[C6066](../code-quality/c6066.md)|Пропущен аргумент-указатель функции форматирования|
|[C6067](../code-quality/c6067.md)|Пропущен аргумент указателя на строку для функции форматирования|
|[C6101](../code-quality/c6101.md)|Возврат неинициализированной памяти|
|[C6200](../code-quality/c6200.md)|Индекс превышает максимальный размер буфера|
|[C6201](../code-quality/c6201.md)|Индекс превышает максимальный размер буфера стека|
|[C6214](../code-quality/c6214.md)|Недействительный литой HRESULT к BOOL|
|[C6215](../code-quality/c6215.md)|Недействительный литой BOOL К HRESULT|
|[C6216](../code-quality/c6216.md)|Недействительный компилятор-вставленный cast BOOL К HRESULT|
|[C6217](../code-quality/c6217.md)|Недействительный тест HRESULT с НЕ|
|[C6220](../code-quality/c6220.md)|Недействительный ХВАКТ Уйдесли Сравните с -1|
|[C6226](../code-quality/c6226.md)|Недействительное назначение HRESULT до -1|
|[C6230](../code-quality/c6230.md)|Недействительный HRESULT Использование как Boolean|
|[C6235](../code-quality/c6235.md)|Ненулевой констант с логическим или|
|[C6236](../code-quality/c6236.md)|Логический или с ненулевой константой|
|[C6237](../code-quality/c6237.md)|Ноль с логическими и теряет побочные эффекты|
|[C6242](../code-quality/c6242.md)|Местное принудительное раскручивание|
|[C6248](../code-quality/c6248.md)|Создание Null DACL|
|[C6250](../code-quality/c6250.md)|Неизданные адреса дескрипторов|
|[C6255](../code-quality/c6255.md)|Незащищенное использование аллокии|
|[C6258](../code-quality/c6258.md)|Использование потока завершения|
|[C6259](../code-quality/c6259.md)|Мертвый код в Bitwise-или ограниченный переключатель|
|[C6260](../code-quality/c6260.md)|Использование Байт Арифметика|
|[C6262](../code-quality/c6262.md)|Чрезмерное использование стеков|
|[C6263](../code-quality/c6263.md)|Использование Alloca в петле|
|[C6268](../code-quality/c6268.md)|Пропавшие без вести скобки в ролях|
|[C6269](../code-quality/c6269.md)|Указатель Dereference Игнорируется|
|[C6270](../code-quality/c6270.md)|Пропущен аргумент с плавающей запятой для функции форматирования|
|[C6271](../code-quality/c6271.md)|Лишний аргумент у функции форматирования|
|[C6272](../code-quality/c6272.md)|Аргумент не с плавающей запятой у функции форматирования|
|[C6273](../code-quality/c6273.md)|Нецелочисленный аргумент у функции форматирования|
|[C6274](../code-quality/c6274.md)|Несимвольный аргумент у функции форматирования|
|[C6276](../code-quality/c6276.md)|Недопустимое приведение строки|
|[C6277](../code-quality/c6277.md)|Недопустимый вызов CreateProcess|
|[C6278](../code-quality/c6278.md)|Array-Новый Scalar-Удалить Несоответствие|
|[C6279](../code-quality/c6279.md)|Scalar-Новый Array-Удалить Несоответствие|
|[C6280](../code-quality/c6280.md)|Распределение памяти-сделка Несоответствие|
|[C6281](../code-quality/c6281.md)|Bitwise Отношение Приоритет|
|[C6282](../code-quality/c6282.md)|Назначение Заменяет тест|
|[C6283](../code-quality/c6283.md)|Примитивный Array-Новый Scalar-Удалить Несоответствие|
|[C6284](../code-quality/c6284.md)|Недопустимый объект в качестве аргумента функции форматирования|
|[C6285](../code-quality/c6285.md)|Логическо-или константы|
|[C6286](../code-quality/c6286.md)|Ненулевой логических или потери побочных эффектов|
|[C6287](../code-quality/c6287.md)|Излишний тест|
|[C6288](../code-quality/c6288.md)|Взаимная интеграция над логическим и является ложным|
|[C6289](../code-quality/c6289.md)|Взаимное исключение над логическим-или верно|
|[C6290](../code-quality/c6290.md)|Приоритет логического НЕ и побитового И|
|[C6291](../code-quality/c6291.md)|Приоритет логического НЕ и побитового ИЛИ|
|[C6292](../code-quality/c6292.md)|Петля подсчитывает вверх от максимума|
|[C6293](../code-quality/c6293.md)|Петля отсчитывает вниз от минимума|
|[C6294](../code-quality/c6294.md)|Тело петли никогда не выполнено|
|[C6295](../code-quality/c6295.md)|Бесконечная петля|
|[C6296](../code-quality/c6296.md)|Петля выполнена только один раз|
|[C6297](../code-quality/c6297.md)|Результат смены литые в больших размерах|
|[C6299](../code-quality/c6299.md)|Битфилд для Булеана Сравнение|
|[C6302](../code-quality/c6302.md)|Недопустимый аргумент в виде строки символов у функции форматирования|
|[C6303](../code-quality/c6303.md)|Недопустимый аргумент в виде строки расширенных символов у функции форматирования|
|[C6305](../code-quality/c6305.md)|Несоответствие размера и количества|
|[C6306](../code-quality/c6306.md)|Недопустимый переменный аргумент при вызове функции|
|[C6308](../code-quality/c6308.md)|Утечка Realloc|
|[C6310](../code-quality/c6310.md)|Незаконные исключения Фильтр Постоянный|
|[C6312](../code-quality/c6312.md)|Исключение Продолжить выполнение петли|
|[C6314](../code-quality/c6314.md)|Bitwise-Или Приоритет|
|[C6317](../code-quality/c6317.md)|Не дополнение|
|[C6318](../code-quality/c6318.md)|Исключение Продолжить поиск|
|[C6319](../code-quality/c6319.md)|Игнорируется запятой|
|[C6324](../code-quality/c6324.md)|Строка Копия вместо строки Сравнить|
|[C6328](../code-quality/c6328.md)|Возможное несоответствие типа аргумента|
|[C6331](../code-quality/c6331.md)|Флаги VirtualFree недействительными|
|[C6332](../code-quality/c6332.md)|VirtualFree Недействительный параметр|
|[C6333](../code-quality/c6333.md)|VirtualFree Недействительный размер|
|[C6335](../code-quality/c6335.md)|Ручка процесса утечки|
|[C6381](../code-quality/c6381.md)|Отсутствует информация о выключении|
|[C6383](../code-quality/c6383.md)|Элемент-Граф Байт-Граф Буфер Перезапуска|
|[C6384](../code-quality/c6384.md)|Подразделение размера указателя|
|[C6385](../code-quality/c6385.md)|Переполнение при чтении|
|[C6386](../code-quality/c6386.md)|Переполнение при записи|
|[C6387](../code-quality/c6387.md)|Недопустимое значение параметра|
|[C6388](../code-quality/c6388.md)|Недопустимое значение параметра|
|[C6500](../code-quality/c6500.md)|Недопустимое свойство атрибута|
|[C6501](../code-quality/c6501.md)|Конфликт значений свойств атрибутов|
|[C6503](../code-quality/c6503.md)|Ссылки не могут быть пустыми (NULL)|
|[C6504](../code-quality/c6504.md)|Значение NULL у переменной, не являющейся указателем|
|[C6505](../code-quality/c6505.md)|MustCheck для Void|
|[C6506](../code-quality/c6506.md)|Размер буфера для массива или переменной, не являющейся указателем|
|[C6508](../code-quality/c6508.md)|Попытка записи константы|
|[C6509](../code-quality/c6509.md)|Использование return в предусловии|
|[C6510](../code-quality/c6510.md)|Завершение нулем у переменной, не являющейся указателем|
|[C6511](../code-quality/c6511.md)|Свойство MustCheck должно иметь значение Yes или No|
|[C6513](../code-quality/c6513.md)|Размер элемента без размера буфера|
|[C6514](../code-quality/c6514.md)|Размер буфера превышает размер массива|
|[C6515](../code-quality/c6515.md)|Размер буфера для переменной, не являющейся указателем|
|[C6516](../code-quality/c6516.md)|Нет свойств у атрибута|
|[C6517](../code-quality/c6517.md)|Допустимый размер у буфера, недоступного для чтения|
|[C6518](../code-quality/c6518.md)|Записываемый размер у буфера, недоступного для записи|
|[C6522](../code-quality/c6522.md)|Недопустимый размер у строкового типа|
|[C6525](../code-quality/c6525.md)|Недоступное расположение у строки недопустимого размера|
|[C6527](../code-quality/c6527.md)|Недопустимая аннотация: свойство "NeedsRelease" не может использоваться для значений типа void|
|[C6530](../code-quality/c6530.md)|Неизвестный стиль строки формата|
|[C6540](../code-quality/c6540.md)|Если для данной функции использовать аннотации атрибута, все ее существующие аннотации __declspec станут недействительными|
|[C6551](../code-quality/c6551.md)|Недопустимая спецификация размера: синтаксический анализ выражения невозможен|
|[C6552](../code-quality/c6552.md)|Недопустимый Deref= или Notref=: синтаксический анализ выражения невозможен|
|[C6701](../code-quality/c6701.md)|Значение не является одним из допустимых значений (Yes/No/Maybe):|
|[C6702](../code-quality/c6702.md)|Значение не является строковым|
|[C6703](../code-quality/c6703.md)|Значение не является числом|
|[C6704](../code-quality/c6704.md)|Непредвиденная ошибка выражения аннотации|
|[C6705](../code-quality/c6705.md)|Ожидаемое число аргументов для аннотации не совпадает с фактическим числом аргументов|
|[C6706](../code-quality/c6706.md)|Непредвиденная ошибка аннотации|
|[C6995](../code-quality/c6995.md)|Не удалось сохранить файл журнала XML|
|[C26100](../code-quality/c26100.md)|Состояние гонки|
|[C26101](../code-quality/c26101.md)|Неиспользование взаимосвязанных операций должным образом|
|[C26110](../code-quality/c26110.md)|Вызывающее неудержание блокировки|
|[C26111](../code-quality/c26111.md)|Вызов не выпустить блокировку|
|[C26112](../code-quality/c26112.md)|Звонящее не может удерживать блокировку|
|[C26115](../code-quality/c26115.md)|Неспособность освободить блокировку|
|[C26116](../code-quality/c26116.md)|Неспособность приобрести или удерживать блокировку|
|[C26117](../code-quality/c26117.md)|Освобождение нехлаженого замка|
|[C26140](../code-quality/c26140.md)|Ошибка аннотации SAL|
|[C26441](../code-quality/c26441.md)|NO_UNNAMED_GUARDS|
|[C26444](../code-quality/c26444.md)|NO_UNNAMED_RAII_OBJECTS|
|[C26498](../code-quality/c26498.md)|USE_CONSTEXPR_FOR_FUNCTIONCALL|
|[C28020](../code-quality/c28020.md)|Выражение не соответствует действительности при этом вызове|
|[C28021](../code-quality/c28021.md)|Аннотируемый параметр должен быть указателем|
|[C28022](../code-quality/c28022.md)|Класс функции (es) на этой функции не соответствует классу функций (es) на typedef, используемом для его определения.|
|[C28023](../code-quality/c28023.md)|Функция, назначенная или пройдена,\_ должна иметь аннотацию класса \_функций\_по крайней мере для одного из классов (es)|
|[C28024](../code-quality/c28024.md)|Указатель функции, к которому присваивается, аннотируется с классом функций, который не содержится в списке класса функций (es).|
|[C28039](../code-quality/c28039.md)|Тип фактического параметра должен точно соответствовать типу|
|[C28112](../code-quality/c28112.md)|Переменная, доступ к которой осуществляется через функцию Interlocked, всегда должна быть доступна через функцию Interlocked.|
|[C28113](../code-quality/c28113.md)|Доступ к локальной переменной через функцию Interlocked|
|[C28125](../code-quality/c28125.md)|Функция должна вызываться из блока try/except|
|[C28137](../code-quality/c28137.md)|Переменный аргумент должен быть (буквальным) постоянным|
|[C28138](../code-quality/c28138.md)|Постоянный аргумент должен быть переменным|
|[C28159](../code-quality/c28159.md)|Вместо этого рассмотрите возможность использования другой функции.|
|[C28160](../code-quality/c28160.md)|Ошибка аннотации|
|[C28163](../code-quality/c28163.md)|Функция никогда не должна вызываться из блока try/except|
|[C28164](../code-quality/c28164.md)|Аргумент передается функции, которая ожидает указатель на объект (не указатель на указатель)|
|[C28182](../code-quality/c28182.md)|Разыменование пустого (NULL) указателя. Этот указатель содержит то же значение NULL, которое содержал другой указатель.|
|[C28183](../code-quality/c28183.md)|Аргумент может быть одним значением, и является копией значения, найденного в указателе|
|[C28193](../code-quality/c28193.md)|Переменная содержит значение, которое должно быть рассмотрено|
|[C28196](../code-quality/c28196.md)|Требование не выполнено. (Выражение не оценивается как истинное.)|
|[C28202](../code-quality/c28202.md)|Недопустимая ссылка на нестатический член|
|[C28203](../code-quality/c28203.md)|Неоднозначная ссылка на член класса.|
|[C28205](../code-quality/c28205.md)|\_Успех\_ \_или\_\_ неудача, используемая в незаконном контексте|
|[C28206](../code-quality/c28206.md)|Левый операнд указывает на структуру, используйте "->"|
|[C28207](../code-quality/c28207.md)|Левый операнд является структурой, используйте "."|
|[C28209](../code-quality/c28209.md)|Декларация символа имеет противоречивую декларацию|
|[C28210](../code-quality/c28210.md)|Аннотации для контекста _on_failure_ не должны находиться в явном предконтексте|
|[C28211](../code-quality/c28211.md)|Для SAL_context ожидалось имя статического контекста|
|[C28212](../code-quality/c28212.md)|Для аннотации ожидалось выражение указателя|
|[C28213](../code-quality/c28213.md)|Аннотация \_\_аннотации\_ «Использование\_декламации» должна использоваться для ссылки без каких-либо изменений на предыдущую декларацию.|
|[C28214](../code-quality/c28214.md)|Допустимые имена параметров атрибута: p1...p9|
|[C28215](../code-quality/c28215.md)|typefix нельзя применять к параметру, который уже имеет typefix|
|[C28216](../code-quality/c28216.md)|Аннотация checkReturn применяется только к постусловиям для конкретного параметра функции.|
|[C28217](../code-quality/c28217.md)|Для функции число параметров у аннотации не совпадает с числом в файле|
|[C28218](../code-quality/c28218.md)|Для параметра функции параметр аннотации не совпадает с параметром, найденным в файле|
|[C28219](../code-quality/c28219.md)|Для параметра аннотации ожидался член перечисления|
|[C28220](../code-quality/c28220.md)|Для параметра аннотации ожидалось целочисленное выражение|
|[C28221](../code-quality/c28221.md)|Для параметра аннотации ожидалось строковое выражение|
|[C28222](../code-quality/c28222.md)|Для аннотации ожидалось __yes, \__no или \__maybe|
|[C28223](../code-quality/c28223.md)|Не найден ожидаемый токен/идентификатор для аннотации, параметр|
|[C28224](../code-quality/c28224.md)|Аннотации требуются параметры|
|[C28225](../code-quality/c28225.md)|Не найдено правильное число обязательных параметров в аннотации|
|[C28226](../code-quality/c28226.md)|Аннотация не может также быть PrimOp (в текущем объявлении)|
|[C28227](../code-quality/c28227.md)|Аннотация не может также быть PrimOp (см. предыдущее объявление)|
|[C28228](../code-quality/c28228.md)|Параметр аннотации: невозможно использовать тип в аннотации|
|[C28229](../code-quality/c28229.md)|Аннотация не поддерживает параметры|
|[C28230](../code-quality/c28230.md)|Тип параметра не содержит членов.|
|[C28231](../code-quality/c28231.md)|Аннотация допустима только для массива|
|[C28232](../code-quality/c28232.md)|Ни к одной аннотации не применено pre, post или deref|
|[C28233](../code-quality/c28233.md)|Pre, post или deref применено к блоку|
|[C28234](../code-quality/c28234.md)|Выражение _At_ не применяется к текущей функции|
|[C28235](../code-quality/c28235.md)|Функция не может использоваться изолированно как аннотация|
|[C28236](../code-quality/c28236.md)|Аннотацию нельзя использовать в выражениях|
|[C28237](../code-quality/c28237.md)|Аннотация в параметре больше не поддерживается|
|[C28238](../code-quality/c28238.md)|Аннотация в параметре содержит несколько значений value, stringValue и longValue. Используйте paramn=xxx|
|[C28239](../code-quality/c28239.md)|Аннотация в параметре одновременно содержит значение value, stringValue или longValue и выражение paramn=xxx. Используйте только paramn=xxx|
|[C28240](../code-quality/c28240.md)|Аннотация в параметре содержит param2, но не содержит param1|
|[C28241](../code-quality/c28241.md)|Аннотация для функции в параметре не распознана|
|[C28243](../code-quality/c28243.md)|Заметки для функции в параметре требуется больше разыменований, чем допускает фактический аннотируемый тип|
|[C28244](../code-quality/c28244.md)|Аннотация для функции имеет непартируемый параметр/внешнюю аннотацию|
|[C28245](../code-quality/c28245.md)|Заметка для функции добавляет заметки к this в функции, не являющейся членом|
|[C28246](../code-quality/c28246.md)|Аннотация параметра для функции не соответствует типу параметра|
|[C28250](../code-quality/c28250.md)|Несогласованная аннотация функции: предыдущий экземпляр содержит ошибку.|
|[C28251](../code-quality/c28251.md)|Несогласованная аннотация функции: этот экземпляр содержит ошибку.|
|[C28252](../code-quality/c28252.md)|Несогласованная аннотация функции: параметр имеет другие аннотации для этого экземпляра.|
|[C28253](../code-quality/c28253.md)|Несогласованная аннотация функции: параметр имеет другие аннотации для этого экземпляра.|
|[C28254](../code-quality/c28254.md)|dynamic_cast<>() не поддерживается в аннотациях|
|[C28262](../code-quality/c28262.md)|В функции обнаружена синтаксическая ошибка для аннотации|
|[C28263](../code-quality/c28263.md)|Во встроенной функции обнаружена синтаксическая ошибка условной аннотации|
|[C28267](../code-quality/c28267.md)|В аннотациях для функции обнаружена синтаксическая ошибка для аннотации.|
|[C28272](../code-quality/c28272.md)|Аннотация для функции: параметр не согласуется с объявлением функции при проверке|
|[C28273](../code-quality/c28273.md)|Функция: причины не согласуются с объявлением функции|
|[C28275](../code-quality/c28275.md)|Параметр \_для\_\_ значения Макро является нулевым|
|[C28279](../code-quality/c28279.md)|Для символа обнаружен begin без соответствующего end|
|[C28280](../code-quality/c28280.md)|Для символа обнаружен end без соответствующего begin|
|[C28282](../code-quality/c28282.md)|Строки формата должны находиться в предусловиях|
|[C28285](../code-quality/c28285.md)|Для функции синтаксическая ошибка в параметре|
|[C28286](../code-quality/c28286.md)|Для функции синтаксическая ошибка рядом с окончанием|
|[C28287](../code-quality/c28287.md)|Для функции: синтаксическая ошибка в аннотации \_At\_() (не распознано имя параметра)|
|[C28288](../code-quality/c28288.md)|Для функции: синтаксическая ошибка в аннотации \_At\_() (недопустимое имя параметра)|
|[C28289](../code-quality/c28289.md)|Для функции: ReadableTo или WritableTo не содержало спецификацию ограничения в качестве параметра|
|[C28290](../code-quality/c28290.md)|Количество внешних элементов в аннотации для функции превышает фактическое число параметров|
|[C28291](../code-quality/c28291.md)|После NULL/не NULL на уровне разыменовывания 0 параметра не имеет смысла для функции.|
|[C28300](../code-quality/c28300.md)|Несовместимые типы операндов выражения для оператора|
|[C28301](../code-quality/c28301.md)|Для первого объявления функции отсутствуют аннотации.|
|[C28302](../code-quality/c28302.md)|В аннотации обнаружен дополнительный оператор \_Deref\_.|
|[C28303](../code-quality/c28303.md)|В аннотации обнаружен неоднозначный оператор \_Deref\_.|
|[C28304](../code-quality/c28304.md)|Обнаружен неверно размещенный оператор \_Notref\_, применяемый к токену.|
|[C28305](../code-quality/c28305.md)|При синтаксическом анализе токена обнаружена ошибка.|
|[C28306](../code-quality/c28306.md)|Аннотация по параметру устаревает|
|[C28307](../code-quality/c28307.md)|Аннотация по параметру устаревает|
|[C28350](../code-quality/c28350.md)|Заметка описывает ситуацию, к которой неприменимы условия.|
|[C28351](/cpp/code-quality/c28351)|Аннотация описывает ситуацию, когда динамическое значение (переменная) не может использоваться в условии.|
