---
title: Параметры, текстовый редактор, все языки
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.General
- VS.ToolsOptionsPages.Text_Editor.ResJSON.General
- VS.ToolsOptionsPages.Text_Editor.All_Languages.General
- VS.ToolsOptionsPages.Text_Editor.Basic.General
- VS.ToolsOptionsPages.Text_Editor.CSharp.General
- VS.ToolsOptionsPages.Text_Editor.C/C++.General
- VS.ToolsOptionsPages.Text_Editor.CoffeeScript.General
- VS.ToolsOptionsPages.Text_Editor.CSS.General
- VS.ToolsOptionsPages.Text_Editor.Dockerfile.General
- VS.ToolsOptionsPages.Text_Editor.F#.General
- VS.ToolsOptionsPages.Text_Editor.Fsharp.General
- VS.ToolsOptionsPages.Text_Editor.HQL.General
- VS.ToolsOptionsPages.Text_Editor.HTML.General
- VS.ToolsOptionsPages.Text_Editor.HTML_(Web_Forms).General
- VS.ToolsOptionsPages.Text_Editor.JavaScript.General
- VS.ToolsOptionsPages.Text_Editor.TypeScript.General
- VS.ToolsOptionsPages.Text_Editor.JSON.General
- VS.ToolsOptionsPages.Text_Editor.LESS.General
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.General
- VS.ToolsOptionsPages.Text_Editor.SCSS.General
- VS.TOOLSOPTIONSPAGES.TEXT_EDITOR.SQL_SERVER_TOOLS.GENERAL
- VS.ToolsOptionsPages.Text_Editor.StreamAnalytics.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.General
- VS.ToolsOptionsPages.Text_Editor.U-SQL.General
- VS.ToolsOptionsPages.Text_Editor.XAML.General
- VS.ToolsOptionsPages.Text_Editor.XML.General
helpviewer_keywords:
- Text Editor Options dialog box
- statement completion
- word wrap
- General dialog box
- line numbers
- virtual space
ms.assetid: 49ee7306-9d46-4170-850f-a1716171752d
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9815bdec94ce32a3bfcc170dd95d834bc43ea58f
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "75566882"
---
# <a name="options-dialog-box-text-editor--all-languages"></a>Диалоговое окно "Параметры": Текстовый редактор \> "Все языки"

Это диалоговое окно позволяет изменять стандартное поведение редактора кода. Эти параметры также применяются к другим редакторам, основанным на редакторе кода, таким как представление исходного кода в конструкторе HTML. Чтобы открыть это диалоговое окно, выберите в меню **Сервис** пункт **Параметры**. В папке **Текстовый редактор** разверните подпапку **Все языки**, а затем выберите **Общие**.

> [!CAUTION]
> На этой странице задаются параметры по умолчанию для всех языков разработки. Не забывайте, что сброс параметра в этом диалоговом окне приведет к возврату общих параметров для всех языков к выбранному здесь значению. Чтобы изменить параметры текстового редактора только для одного языка, раскройте подпапку для этого языка и выберите соответствующие страницы параметров.

Неактивная галочка отображается в том случае, если параметр был выбран на странице общих параметров для некоторых, но не для всех языков программирования.

## <a name="statement-completion"></a>Завершение операторов

**Автоматически отображать список членов**

Если этот флажок установлен, технология IntelliSense отображает всплывающие списки доступных членов, свойств, значений или методов при вводе в редакторе. Выберите любой элемент в раскрывающемся списке, чтобы вставить его в код. При выборе этого параметра включается параметр **Скрывать дополнительные члены**.

**Скрывать дополнительные члены**

Если этот флажок установлен, раскрывающиеся списки завершения инструкций сокращаются и в них выводятся только наиболее часто используемые элементы. Другие элементы будут отфильтрованы из списка.

**Сведения о параметрах**

Если этот флажок установлен, под точкой вставки в редакторе отображается полный синтаксис текущего объявления для процедуры со всеми доступными параметрами. Очередной параметр, который может быть присвоен, выделяется полужирным шрифтом.

## <a name="settings"></a>Параметры

**Включить виртуальное пространство**

Если этот флажок установлен, а флажок **Перенос по словам** снят, можно щелкать и вводить текст в любом месте после конца строки текста в редакторе кода. Эта возможность может использоваться для единообразного позиционирования комментариев вслед за кодом.

**Переносить по словам**

Если этот флажок установлен, то часть длинной текстовой строки, выходящая за пределы видимой области редактора, автоматически отображается на следующей строке. Выбор этого параметра приводит к включению параметра **Показывать графические метки в местах переноса слов**.

> [!NOTE]
> Функция **Виртуальное пространство** отключена, если включен параметр **Перенос по словам**.

**Показывать визуальные глифы для переноса по словам**

Если этот флажок установлен, в том месте, где длинная текстовая строка переносится на следующую строку, отображается индикатор стрелки возврата каретки.

![Снимок экрана LineBreakSymbol](../../ide/reference/media/linebreak.gif)

Снимите этот флажок, если не требуется отображать эти стрелки.

> [!NOTE]
> Эти стрелки-напоминания не добавляются в код и не выводятся на печать. Они предназначены только для справки.

**Номера строк**

Если флажок установлен, рядом с каждой строкой кода отображается номер строки.

> [!NOTE]
> Эти номера строк не добавляются в код и не печатаются. Они предназначены только для справки.

**Открывать URL-адреса однократным щелчком**

Если этот флажок установлен, курсор мыши будет принимать форму указателя-руки при наведении на URL-адрес в редакторе. Можно щелкнуть URL-адрес для отображения указанной страницы в браузере.

**Панель навигации**

Если этот флажок установлен, **панель навигации** отображается в верхней части редактора кода. Раскрывающиеся списки **объектов** и **членов** панели позволяют выбрать конкретный объект в коде, выбрать его члены и перейти к объявлению выбранного члена в редакторе кода.

**Применять команды "Вырезать" или "Копировать" к пустым строкам, если отсутствует выбранный текст**

Этот параметр задает поведение редактора в ситуации, когда пользователь помещает курсор в пустую строку, ничего не выбирает и затем пытается что-либо скопировать или вырезать.

- Если флажок установлен, то копируется или вырезается пустая строка. Если затем произвести вставку, будет вставлена новая пустая строка.

- Если этот флажок снят, команды вырезания удаляет пустые строки. Тем не менее, данные сохраняются в буфере обмена. Таким образом, если затем используется команда "Вставить", вставляется последнее содержимое, скопированное в буфер обмена. Если ничего не было ранее скопировано, вставка не произойдет.

Этот параметр не влияет на команды "Копировать" и "Вырезать", если строка не пуста. Если ничего не выделено, копируется или вырезается вся строка. Если затем произвести вставку, будет вставлен текст всей строки и ее завершающий символ.

> [!TIP]
> Чтобы отображались индикаторы для пробелов, знаков табуляции и символов конца строки, что позволяет отличать строки, обозначенные отступом, от полностью пустых строк, выберите **Дополнительно** в меню **Правка** и задайте **Показать пустое пространство**.

## <a name="see-also"></a>См. также

- ["Параметры", "Текстовый редактор", "Все языки", "Вкладки"](../../ide/reference/options-text-editor-all-languages-tabs.md)
- [Страница "Общие", папка "Среда", диалоговое окно "Параметры"](../../ide/reference/general-environment-options-dialog-box.md)
- [Использование технологии IntelliSense](../../ide/using-intellisense.md)
