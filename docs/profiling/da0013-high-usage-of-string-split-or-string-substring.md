---
title: DA0013. Интенсивное использование String.Split или String.Substring | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.13
- vs.performance.rules.DAAvoidStringSubstr
- vs.performance.DA0013
- vs.performance.rules.DA0013
helpviewer_keywords:
- vs.performance.13
- vs.performance.rules.DA0013
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: d42469ac5236a41eda96af5d1fe896a5ed84a321
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779413"
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013: интенсивное использование String.Split или String.Substring

|||
|-|-|
|Идентификатор правила|DA0013|
|Категория|Руководство по использованию .NET Framework|
|Методы профилирования|Выборка|
|Сообщение|Рекомендуется снизить использование функций String.Split и String.Substring.|
|Тип правила|Предупреждение|

## <a name="cause"></a>Причина
 Вызовы методов System.String.Split и System.String.Substring составляют значительную часть данных профилирования. Рекомендуется использовать метод System.String.IndexOf или System.String.IndexOfAny при проверке существования подстроки в строке.

## <a name="rule-description"></a>Описание правила
 Метод Split обрабатывает объект типа "строка" и возвращает массив строк, содержащих подстроки исходной строки. Функция выделяет память для возвращаемого объекта типа "массив" и для новых объектов типа "строка" для каждого элемента массива. Аналогичным образом метод Substr обрабатывает объект типа "строка" и возвращает новую строку, эквивалентную запрошенной подстроке.

 Если приложение критично к управлению выделением памяти, рассмотрите возможность использования других методов вместо String.Split и String.Substr. Например, можно использовать метод IndexOf или IndexOfAny для поиска конкретной подстроки в строке символов без создания нового экземпляра класса String.

## <a name="how-to-investigate-a-warning"></a>Изучение причин предупреждения
 Дважды щелкните сообщение в окне **Список ошибок**, чтобы перейти к представлению [Сведения о функциях](../profiling/function-details-view.md) выборки данных профилирования. Проверьте вызовы функций, чтобы найти участки программы, в которых наиболее часто используются методы System.String.Split и System.String.Substr. По возможности старайтесь использовать методы IndexOf и IndexOfAny для поиска нужной подстроки в строке символов без создания нового экземпляра класса String.
