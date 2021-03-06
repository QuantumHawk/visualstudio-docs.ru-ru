---
title: Псевдонимы команд | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- aliases, Visual Studio commands
- Visual Studio, commands
- predefined command aliases
- commands, aliases
- Visual Studio commands
- pre-defined command aliases
- command aliases
ms.assetid: de8bb378-8c1c-4087-a9a5-537fa8314c19
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7e9419e64cd211490fc1d3785045b5de117d392e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72657855"
---
# <a name="visual-studio-command-aliases"></a>Visual Studio Command Aliases
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Псевдонимы предоставляют средства для ввода команд в **Найти** или в окне **Команда**, сокращая текст, необходимый для набора выполняемых команд. Например, чтобы не вводить `>File.OpenFile` для отображения диалогового окна **Открытие файла**, можно использовать стандартный псевдоним `>of`.

 Введите `alias` в окне **Команда**, чтобы отобразить список текущих псевдонимов и их определений. Введите `>cls`, чтобы очистить окно **Команда**. Если требуется просмотреть псевдоним для конкретной команды, введите `alias <command name>`.

 Можно легко создать собственный псевдоним для одной из команд Visual Studio (с аргументами или без них). Например, синтаксис для создания псевдонимов `File.NewFile MyFile.txt` — `alias MyAlias File.NewFile MyFile.txt`. С помощью `alias <alias name> /delete` можно удалить один из псевдонимов.

 В следующей таблице содержится список предопределенных псевдонимов команд Visual Studio. Некоторые имена команд имеют несколько предварительно определенных псевдонимов. Щелкните ссылки для имен команд, чтобы открыть разделы, в которых подробно объясняются правильный синтаксис, аргументы и параметры для этих команд.

|Имя команды|Alias|Полное имя|
|------------------|-----------|-------------------|
|[Команда "Печать"](../../ide/reference/print-command.md)|?|Debug.Print|
|[Команда "Быстрая проверка"](../../ide/reference/quick-watch-command.md)|??|Debug.QuickWatch|
|Добавление нового проекта|AddProj|File.AddNewProject|
|[Команда Alias](../../ide/reference/alias-command.md)|Alias|Tools.Alias|
|Видимые - окно|Автоматические|Debug.Autos|
|Точки останова - окно|bl|Debug.Breakpoints|
|Точка останова|bp|Debug.ToggleBreakpoint|
|Стек вызовов - окно|CallStack|Debug.CallStack|
|Clear Bookmarks|ClearBook|Edit.ClearBookmarks|
|Закрыть|Закрыть|File.Close|
|Close All Documents|CloseAll|Window.CloseAllDocuments|
|Очистить все|cls|Edit.ClearAll|
|Режим команд|cmd|View.CommandWindow|
|Перейти к коду|код|View.ViewCode|
|[Команда "Вывести память"](../../ide/reference/list-memory-command.md)|дн.|Debug.ListMemory|
|[Команда List Memory](../../ide/reference/list-memory-command.md) как ANSI|da|Debug.ListMemory /Ansi|
|[Команда List Memory](../../ide/reference/list-memory-command.md) в однобайтовом формате|db|Debug.ListMemory /Format:OneByte|
|[Команда List Memory](../../ide/reference/list-memory-command.md) как ANSI с 4-байтовым форматом|dc|Debug.ListMemory /Format:FourBytes /Ansi|
|[Команда List Memory](../../ide/reference/list-memory-command.md) в четырехбайтовом формате|dd|Debug.ListMemory /Format:FourBytes|
|Удалить до начала строки|DelBOL|Edit.DeleteToBOL|
|Удалить до конца строки|DelEOL|Edit.DeleteToEOL|
|Удалить пустое пространство по горизонтали|DelHSp|Edit.DeleteHorizontalWhitespace|
|Конструктор представлений|конструктор|View.ViewDesigner|
|[Команда List Memory](../../ide/reference/list-memory-command.md) в формате с плавающей точкой|df|Debug.ListMemory/Format:Float|
|Дизассемблирование - окно|disasm|Debug.Disassembly|
|[Команда List Memory](../../ide/reference/list-memory-command.md) в восьмибайтовом формате|dq|Debug.ListMemory /Format:EightBytes|
|[Команда List Memory](../../ide/reference/list-memory-command.md) как Юникод|du|Debug.ListMemory /Unicode|
|[Команда "Вычислить оператор"](../../ide/reference/evaluate-statement-command.md)|eval|Debug.EvaluateStatement|
|Exit|Exit|File.Exit|
|Форматировать выделенный фрагмент|format|Edit.FormatSelection|
|Во весь экран|Полный экран|View.FullScreen|
|[Команда Start](../../ide/reference/start-command.md)|н|Debug.Start|
|[Команда "Перейти"](../../ide/reference/go-to-command.md)|GotoLn|Edit.GoTo|
|Перейти к скобке|GotoBrace|Edit.GotoBrace|
|F1Help|Справка|Help.F1Help|
|Режим интерпретации|immed|Tools.ImmediateMode|
|Вставить файл как текст|InsertFile|Edit.InsertFileAsText|
|[Команда "Вывести стек вызовов"](../../ide/reference/list-call-stack-command.md)|kb|Debug.ListCallStack|
|Нижний регистр|Lcase|Edit.MakeLowercase|
|Вырезать строку|LineCut|Edit.LineCut|
|Удалить строку|LineDel|Edit.LineDelete|
|Список членов|ListMembers|Edit.ListMembers|
|Локальные - окно|Локальные|Debug.Locals|
|[Команда "Запись вывода окна команд"](../../ide/reference/log-command-window-output-command.md)|Журнал|Tools.LogCommandWindowOutput|
|Режим пометки окна команд|mark|Tools.CommandWindowMarkMode|
|Память - окно|Memory Memory1|Debug.Memory1|
|Окно "Память 2"|Memory2|Debug.Memory2|
|Окно "Память 3"|Memory3|Debug.Memory3|
|Окно "Память 4"|Memory4|Debug.Memory4|
|[Команда "Задать основание системы счисления"](../../ide/reference/set-radix-command.md)|n|Debug.SetRadix|
|[Команда ShowWebBrowser](../../ide/reference/showwebbrowser-command.md)|nav navigate|View.ShowWebBrowser|
|Следующая закладка|NextBook|Edit.NextBookmark|
|[Команда "Создать файл"](../../ide/reference/new-file-command.md)|nf|File.NewFile|
|Создание проекта|np NewProj|File.NewProject|
|[Команда "Открыть файл"](../../ide/reference/open-file-command.md)|of Open|File.OpenFile|
|[Команда "Открыть проект"](../../ide/reference/open-project-command.md)|op|File.OpenProject|
|Свернуть в определения/прекратить показ структуры|OutlineDefs StopOutlining|Edit.CollapsetoDefinitions|
|Шаг с обходом|p|Debug.StepOver|
|Сведения о параметрах|ParamInfo|Edit.ParameterInfo|
|Шаг с выходом|pr|Debug.StepOut|
|Предыдущая закладка|PrevBook|Edit.PreviousBookmark|
|Печать файла|print|File.Print|
|Окно \"Свойства\"|props|View.PropertiesWindow|
|Остановить|q|Debug.StopDebugging|
|Повторить|redo|Edit.Redo|
|Регистры - окно|регистры|Debug.Registers|
|Выполнить до текущей позиции|rtc|Debug.RunToCursor|
|Сохранить выбранные элементы|save|File.SaveSelectedItems|
|Сохранить все|SaveAll|File.SaveAll|
|Сохранить как|SaveAs|File.SaveSelectedItemsAs|
|[Команда "Оболочка"](../../ide/reference/shell-command.md)|оболочка|Tools.Shell|
|Остановить поиск в файлах|StopFind|Edit.FindInFiles /stop|
|Переставить закрепление|SwapAnchor|Edit.SwapAnchor|
|Шаг с заходом|т|Debug.StepInto|
|Заполнить выделенный фрагмент знаками табуляции|преобразование в знаки табуляции|Edit.TabifySelection|
|Окно "Список задач"|TaskList|View.TaskList|
|Потоки - окно|Потоки|Debug.Threads|
|Сверху вниз|TileH|Window.TileHorizontally|
|Слева направо|TileV|Window.TileVertically|
|Закладка|ToggleBook|Edit.ToggleBookmark|
|Окно "Панель элементов"|панель элементов|View.Toolbox|
|[Команда "Вывести дизассемблированный код"](../../ide/reference/list-disassembly-command.md)|u|Debug.ListDisassembly|
|Все прописные|Ucase|Edit.MakeUppercase|
|Отменить|undo|Edit.Undo|
|Отменить заполнение выделенного фрагмента знаками табуляции|Untabify|Edit.UntabifySelection|
|Контрольные значения - окно|Контрольное значение|Debug.WatchN|
|Включить перенос по словам|WordWrap|Edit.ToggleWordWrap|
|Вывести процессы|&#124;|Debug.ListProcesses|
|[Команда "Вывести потоки"](../../ide/reference/list-threads-command.md)|~ ~*k ~\*kb|Debug.ListThreads Debug.ListTheads /AllThreads|

## <a name="see-also"></a>См. также раздел
 Команда [Visual Studio командное](../../ide/reference/visual-studio-commands.md) [окно](../../ide/reference/command-window.md) ["Поиск/команда"](../../ide/find-command-box.md)
