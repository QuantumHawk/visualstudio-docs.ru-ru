---
title: Устранение ошибок в программах и улучшение кода
description: В этой статье описываются несколько основных способов, с помощью которых Visual Studio может помочь найти и исправить проблемы в коде, включая ошибки сборки, анализ кода, средства отладки и модульные тесты.
ms.date: 05/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 320615daa95ba9fad69fe48490f83c19ccf8e1ce
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2018
---
# <a name="make-code-work-in-visual-studio"></a>Работа с кодом в Visual Studio

Visual Studio включает эффективный интегрированный набор средств сборки и отладки проектов. Из этой статьи вы узнаете, как Visual Studio может помочь обнаружить проблемы в коде с помощью построения выходных данных, анализа кода, средств отладки и модульных тестов.

Мы разобрались, как работать с редактором, и написали код. Теперь необходимо убедиться, что код работает должным образом. Отладка в Visual Studio, как и в большинстве интегрированных сред разработки (IDE), осуществляется в два этапа: построение кода для обнаружения и устранения ошибок проекта и компилятора и выполнение кода для обнаружения ошибок времени выполнения и динамических ошибок.

## <a name="build-your-code"></a>Сборка кода

Существует два основных типа конфигурации сборки: **отладка** и **выпуск**. При использовании конфигурации **отладка** создается более крупный и медленный исполняемый файл, обеспечивающий более широкие интерактивные возможности отладки во время выполнения. Исполняемый файл конфигурации **отладка** никогда не следует отправлять. Конфигурация **выпуск** позволяет создать более быстрый оптимизированный исполняемый файл, подходящий для отправки (по крайней мере с точки зрения компилятора). По умолчанию используется конфигурация **Отладка**.

Самый простой способ выполнить сборку проекта — нажать клавишу **F7**, однако вы также можете начать сборку, выбрав в главном меню пункты **Сборка** > **Собрать решение**.

![Выбор пункта меню "Построить проект" в Visual Studio](../ide/media/vs_ide_gs_debug_build_menu_item.png)

Процесс сборки можно наблюдать в окне **Вывод** в нижней части пользовательского интерфейса Visual Studio. Здесь отображаются ошибки, предупреждения и операции сборки. При наличии ошибок (или предупреждений выше заданного уровня) сборка завершится ошибкой. Можно щелкнуть ошибку и предупреждение, чтобы перейти к строке, где они возникли. Для перестроения проекта можно нажать клавишу **F7** (чтобы перекомпилировать только файлы с ошибками) или **CTRL**+**ALT**+**F7** (для чистого полного перестроения).

В окне результатов содержатся два окна с вкладками под областью редактора: окно **Вывод**, в котором содержатся необработанные выходные данные компилятора (включая сообщения об ошибках), и окно **Список ошибок**, содержащее список всех ошибок и предупреждений, к которому можно применить сортировку и фильтры.

После успешного выполнения построения вы увидите примерно следующие результаты в окне **Вывод**:

![Выходные данные при успешном построении в Visual Studio](../ide/media/vs_ide_gs_debug_success_build.png)

## <a name="review-the-error-list"></a>Просмотр списка ошибок

Если вы внесли какие-либо изменения в код, который был ранее и успешно скомпилирован, возможно, возникнет ошибка. Если вы новичок в написании кода, возможно, их будет много. Ошибки иногда очевидны, например простая синтаксическая ошибка или неправильное имя переменной, а иногда их причину трудно выяснить, имея в распоряжении только зашифрованный код. Чтобы получить более четкое представление о проблеме, перейдите вниз окна **Вывод** сборки и щелкните вкладку **Список ошибок**. При этом вы перейдете к более организованному представлению ошибок и предупреждений для проекта и получите доступ к некоторым дополнительным параметрам.

![Список ошибок и вывода в Visual Studio](../ide/media/vs_ide_gs_debug_bad_build_error_list.png)

Щелкните строку ошибки в окне **Список ошибок**, чтобы перейти в строку кода, в которой возникла ошибка. (Номера строк также можно включить, щелкнув панель **быстрого запуска** в верхнем правом углу: введите "номера строк" в поле и нажмите клавишу **ВВОД**.) Это самый быстрый способ перехода в диалоговое окно **Параметры**, где можно включить номера строк. Узнайте, как использовать панель **быстрого запуска** и избежать лишних действий в пользовательском интерфейсе.)

![Редактор Visual Studio с номерами строк](../ide/media/vs_ide_gs_debug_line_numbers.png)

![Параметр "Номера строк" в Visual Studio](../ide/media/vs_ide_gs_debug_options_line_numbers.png)

Нажмите клавиши **CTRL**+**G** для быстрого перехода к номеру строки, в которой возникла ошибка.

Ошибку можно узнать по подчеркиванию красной волнистой линией Чтобы получить дополнительные сведения, наведите на нее указатель мыши. Внесите исправления, и подчеркивание исчезнет, хотя в результате исправления может возникнуть новая ошибка (это называется "регрессия").

![Ошибка при наведении курсора мыши в Visual Studio](../ide/media/vs_ide_gs_debug_error_hover1.png)

Пройдите список ошибок и устраните все ошибки в коде.

![Окно ошибок отладчика в Visual Studio](../ide/media/vs_ide_gs_debug_error_list.png)

### <a name="review-errors-in-detail"></a>Просмотр подробных сведений об ошибках

Многие ошибки трудны для восприятия, будучи представленными в терминах компилятора. В этом случае могут потребоваться дополнительные сведения. Из окна **Список ошибок** можно выполнить автоматический поиск в поисковой системе Bing для получения дополнительных сведений об ошибке или предупреждении. Щелкните правой кнопкой мыши по соответствующей строке записи и выберите **Показать справочные сведения об ошибке** из контекстного меню или щелкните гиперссылку с кодом ошибки в столбце **код** в **списке ошибок**.

![Поиск Bing-списка ошибок в Visual Studio](../ide/media/vs_ide_gs_debug_error_list_error_help.png)

В зависимости от настроек результаты поиска по коду и описанию ошибки откроются в веб-браузере либо во вкладке Visual Studio с результатами поиска Bing. Представленные результаты — из различных источников в Интернете, и, возможно, не все они будут полезными.

## <a name="use-code-analysis"></a>Анализ кода

Средства анализа выполняют поиск общих проблем в коде, которые могут привести к ошибкам времени выполнения или проблемам управления кодом.

### <a name="c-and-visual-basic-code-analysis"></a>Анализ кода C# и Visual Basic

Visual Studio 2017 содержит встроенный набор [анализаторов платформы компиляторов .NET](../code-quality/roslyn-analyzers-overview.md), которые проверяют код на C# и Visual Basic при его наборе. Можно установить дополнительные анализаторы в виде расширений Visual Studio или в виде пакетов NuGet. Если обнаруживаются нарушения правил, они помечаются как в редакторе кода (волнистая линия под соответствующим кодом), так и в **списке ошибок**.

### <a name="c-code-analysis"></a>Анализ кода C++

Чтобы выполнить анализ кода C++, запустите [статический анализ кода](../code-quality/quick-start-code-analysis-for-c-cpp.md). Запустить этот компонент после устранения всех очевидных ошибок, препятствующих успешной сборке, и потратить некоторое время, чтобы устранить создаваемые им предупреждения, — очень полезная привычка. Вы сможете избавиться от определенных будущих проблем, а также научитесь некоторым полезным приемам написания кода.

Нажмите клавиши **ALT**+**F11** (или выберите в верхнем меню команду **Анализ** > **Выполнить анализ кода в решении**) для запуска статического анализа кода.

![Элемент меню "Анализ кода" в Visual Studio](../ide/media/vs_ide_gs_debug_run_code_analysis.png)

Все новые или обновленные предупреждения отображаются на вкладке **Список ошибок** в нижней части интегрированной среды разработки. Щелкните предупреждение для перехода к нему в коде.

![Список ошибок с предупреждениями в Visual Studio](../ide/media/cpp-code-analysis-warning.png)

## <a name="use-light-bulbs-to-fix-or-refactor-code"></a>Использование значка лампочки для исправления или рефакторинга кода

[Быстрые действия](../ide/quick-actions.md), доступные с помощью значка лампочки или отвертки, позволяют выполнить встроенный рефакторинг кода. Это простой способ быстрого и эффективного устранения распространенных предупреждений в коде C#, C++ и Visual Basic. Для доступа к ним щелкните правой кнопкой мыши волнистую линию предупреждения и выберите **Быстрые действия и рефакторинг**. Либо, когда курсор находится на строке с цветной волнистой линией, нажмите клавиши **CTRL**+**.** или выберите значок отвертки или лампочки в поле. Вы увидите список возможных исправлений или операций рефакторинга, которые можно применить к соответствующей строке кода.

![Предварительный просмотр лампочки в Visual Studio](../ide/media/quick-actions-options.png)

Быстрые действия можно использовать в любом случае, когда средство анализа кода определяет возможность исправления, рефакторинга или улучшения кода. Щелкните любую строку кода, откройте контекстное меню и выберите пункт **Быстрые действия и рефакторинг**. Если доступны варианты рефакторинга или улучшения, то они будут отображены. В противном случае в левом нижнем углу интегрированной среды разработки появится сообщение **Быстрые действия недоступны**.

![Текст "Быстрые действия недоступны"](../ide/media/vs_ide_gs_debug_light_bulb_no_options.png)

Если вы привыкли работать с клавиатурой, вы можете использовать клавиши со стрелками и сочетание клавиш **CTRL**+**.** для проверки возможностей оптимизации и очистки кода!

## <a name="debug-your-running-code"></a>Отладка выполняемого кода

Успешно завершив сборку кода и его очистку, запустите код, нажав клавишу **F5** или выбрав команду **Отладка** > **Начать отладку**. Приложение будет запущено в среде отладки, и вы сможете пронаблюдать его поведение. Интегрированная среда разработки Visual Studio изменяется во время выполнения приложения: окно **Вывод** заменяется двумя новыми окнами (в конфигурации окон по умолчанию): окном с вкладками **Видимые/Локальные/Контрольные значения** и окном с вкладками **Стек вызовов/Точки останова/Параметры исключений/Вывод**. Эти окна имеют несколько вкладок, которые позволяют просмотреть и проверить переменные, потоки, стеки вызовов приложения и другие характеристики поведения во время выполнения приложения.

![Окна "Видимые" и "Стек вызовов" Visual Studio](../ide/media/vs_ide_gs_debug_autos_and_call_stack.png)

Остановите приложение, нажав клавиши **SHIFT**+**F5** или кнопку **Остановить**. Кроме того, можно просто закрыть главное окно приложения (или диалоговое окно командной строки).

Если код выполняется полностью и точно так, как ожидалось, вас можно поздравить. Но в случае зависания, сбоя или непредвиденных результатов может потребоваться найти источник проблем и исправить ошибки.

### <a name="set-simple-breakpoints"></a>Задание простых точек останова

[Точки останова](../debugger/using-breakpoints.md) — это один из самых простых и важных компонентов надежной отладки. Точка останова указывает, где Visual Studio следует приостановить выполнение кода, чтобы вы могли проверить значения переменных или поведение памяти либо выполнение ветви кода. После установки или удаления точек останова перестраивать проект не нужно.

Установите точку останова, щелкнув дальнее поле строки, в которой требуется приостановить выполнение, или нажмите клавишу **F9**, чтобы установить точку останова в текущей строке кода. Выполнение кода прерывается (*останавливается*) перед инструкциями для этой строки кода.

![Точка останова в Visual Studio](../ide/media/vs_ide_gs_debug_breakpoint1.png)

Чаще всего точки останова используются для решения следующих задач.

- Для сужения области поиска источника сбоя или зависания, когда точки останова устанавливаются в разных местах участка кода вызова метода, который, возможно, является источником проблемы, и за его пределами. При выполнении кода в отладчике удаляйте, а затем снова устанавливайте точки останова ближе друг к другу, пока не найдете строку кода, вызывающую ошибку. Выполнение кода в отладчике описывается в следующем разделе.

- При добавлении нового кода установите точку останова в его начале и выполните код, чтобы убедиться в том, что он работает правильно.

- При реализации сложного поведения задайте точки останова для алгоритмического кода, чтобы можно было проверить значения переменных и данные при прерывании программы.

- При написании кода C или C++ используйте точки останова для остановки кода, чтобы можно было проверить значения адреса (ищите значение NULL) и просмотреть значения счетчиков при отладке ошибок, связанных с памятью.

Дополнительные сведения о точках останова см. в статье [Использование точек останова](../debugger/using-breakpoints.md).

### <a name="inspect-your-code-at-run-time"></a>Проверка кода во время выполнения

Когда выполнение кода приостанавливается из-за достижения точки останова, строка кода, помеченная желтым цветом (текущий оператор), еще не выполнена. Вы можете выполнить текущий оператор и проверить, как изменились значения. Для выполнения кода в отладчике можно использовать ряд команд *пошагового выполнения*. Если отмеченный код является вызовом метода, вы можете выполнить шаг с заходом, нажав клавишу **F11**. Кроме того, можно выполнить *шаг с обходом* строки кода, нажав клавишу **F10**. Дополнительные команды и подробные сведения о пошаговом выполнении кода см. в статье [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md).

![Проверка значения времени выполнения Visual Studio](../ide/media/vs_ide_gs_debug_hit_breakpoint.png)

Код, представленный на предыдущей иллюстрации, может выполняться отладчиком по одному оператору. Для этого можно нажимать клавишу **F10** или **F11** (так как здесь нет вызова метода, результат выполнения обеих команд будет одинаковым).

Когда отладчик приостанавливает выполнение, можно проверить переменные и стеки вызовов, чтобы разобраться в происходящем. Находятся ли значения в тех диапазонах, которые вы ожидали увидеть? Выполняются ли вызовы в правильном порядке?

![Проверка значения времени выполнения Visual Studio](../ide/media/vs_ide_gs_debug_inspect_value.png)

Наведите курсор на переменную для просмотра ее текущего значения и ссылок. Если отображается значение, которое вы не ожидали увидеть, возможно, в предыдущем или вызывающем коде имеется ошибка. Более подробные сведения об отладке см. в статье об [использовании отладчика](../debugger/getting-started-with-the-debugger.md).

Кроме того, Visual Studio выводит на экран окно **средств диагностики**, где можно наблюдать за загрузкой ЦП и использованием памяти приложением в динамике по времени. В дальнейшем в процессе разработки приложения эти средства можно применять для выявления случаев непредвиденно высокой загрузки ЦП или чрезмерного выделения памяти. Это окно можно использовать в сочетании с окном **Контрольные значения** и точками останова, чтобы определить причину непредвиденно интенсивного использования или неосвобожденных ресурсов. Дополнительные сведения см. в статье [Обзор возможностей профилирования](../profiling/profiling-feature-tour.md).

## <a name="run-unit-tests"></a>Запуск модульных тестов

Модульные тесты — это первая линия защиты от ошибок в коде, так как при правильном проведении они позволяют проверять отдельные "модули" кода (как правило, это отдельные функции), которые проще отлаживать, чем всю программу. Visual Studio устанавливает платформу модульного тестирования Майкрософт для управляемого и машинного кода. Платформа модульного тестирования используется для создания модульных тестов, их запуска и передачи результатов таких тестов. Завершив внесение изменений, запустите модульные тесты повторно, чтобы убедиться, что код по-прежнему работает правильно. При использовании выпуска Visual Studio Enterprise можно настроить автоматический запуск тестов после каждой сборки.

Чтобы приступить к работе с модульными тестами, ознакомьтесь со статьей [Создание модульных тестов для кода с помощью IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).

Дополнительные сведения о модульных тестах в Visual Studio, а также о том, как они могут помочь в создании более качественного кода, см. в статье [Основные сведения о модульных тестах](../test/unit-test-basics.md).

## <a name="see-also"></a>См. также

- [Обзор функций отладчика](../debugger/debugger-feature-tour.md)
- [Дополнительные сведения об использовании отладчика](../debugger/getting-started-with-the-debugger.md)
- [Создание и исправление кода](../ide/code-generation-in-visual-studio.md)